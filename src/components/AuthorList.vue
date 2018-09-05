<template>
    <div class="all-author-info">
        <div class="img-div">
            <img :src="`${author.portrait_url}`" alt="an author" />
        </div>
        <div class="author-details">
            <h1> {{author.first_name}} {{author.last_name}}</h1>
            <h2>Author Biography:</h2>
            <p>{{author.biography}}</p>
        </div>
        

    </div>   

</template>


<script>
import Header from './Header'

export default {
    name: "AuthorList",
    components: {
        Header
    },
    data() {
        return {
            
        }
    },
    props: ["author"],
    methods: {
    
    }, 
    mounted() {
        console.log(this.author);
        
    }

}

</script>

<style scoped>

.all-author-info {
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
.author-details {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 40vw;
    margin-left: 3vw;
}

</style>