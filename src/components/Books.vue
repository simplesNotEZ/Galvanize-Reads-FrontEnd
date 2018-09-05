<template>
    <div>
        <Header />
        <div class="books-div">
            <BookList v-for="oneBook in books" :key="oneBook.id" :book="oneBook" />
        </div>
    </div>   

</template>


<script>
import Header from './Header'
import BookList from './BookList'

export default {
    name: "Books",
    components: {
        Header,
        BookList
    },
    data(){
        return {
            books: null
        }
    },
    methods: {
        getData(){
            fetch('https://gal-rds.herokuapp.com/books')
            .then(response => {
                console.log("the response from books fetch: ", response);
                return response.json();
            })
            .then( json => {
                this.books = json.books;
                console.log("here's what's in my books data object: ", this.books);
            });
        }
    },    
    mounted() {
        this.getData()
    }

}

</script>

<style scoped>
.books-div {
    display: flex;
    flex-direction: column;
    align-items: center;
}

</style>