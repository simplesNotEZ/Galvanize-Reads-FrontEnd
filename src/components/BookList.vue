<template>
    <div class="all-book-info">
        <div class="img-div">
            <img :src="`${book.book_cover_url}`" alt="a book" />
        </div>
        <div class="book-details">
            <h1> {{book.book_title}}</h1>
            <div class="authors">
                <h2>By {{book.author_id_one}}</h2>
                <h2 v-if="this.authorTwo">& {{book.author_id_two}}</h2>
                <h2 v-if="this.authorThree">& {{book.author_id_three}}</h2>
            </div>
            <h2>{{book.book_genre}}</h2>
            <p>{{book.book_description}}</p>
        </div>
        

    </div>   

</template>


<script>
import Header from './Header'

export default {
    name: "BookList",
    components: {
        Header
    },
    data() {
        return {
            authorTwo: null,
            authorThree: null
        }
    },
    props: ["book"],
    methods: {
        getAdditionalAuthors(props)  {
            if (props.author_id_two !== "0") {
                this.authorTwo = props.author_id_two;
            }
            if (props.author_id_three !== "0") {
                this.authorThree = props.author_id_three;
            }
        }
    }, 
    mounted() {
        console.log(this.book);
        this.getAdditionalAuthors(this.book);
    }

}

</script>

<style scoped>

.all-book-info {
    display: flex;
    justify-content: flex-start;
    border: .125vw solid black;
    margin-bottom: 1vw;
    width: 70vw;
    
}
.img-div img {
    height: 50vh;
    margin-top: 1vw;
    margin-bottom: 1vw;
    margin-left: 1vw;
}
.book-details {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 40vw;
    margin-left: 3vw;
}
.authors {
    display: flex;
}

</style>