<template>
    <div>
        <Header />
        <div class="authors-div">
            <AuthorList v-for="oneAuthor in authors" :key="oneAuthor.id" :author="oneAuthor" />
        </div>
    </div>   

</template>


<script>
import Header from './Header'
import AuthorList from './AuthorList'

export default {
    name: "Authors",
    components: {
        Header,
        AuthorList
    },
    data(){
        return {
            authors: null
        }
    },
    methods: {
        getData(){
            fetch('https://gal-rds.herokuapp.com/authors')
            .then(response => {
                console.log("the response from authors fetch: ", response);
                return response.json();
            })
            .then( json => {
                this.authors = json.authors;
                console.log("here's what's in my data object for authors: ", this.authors);
            });
        }
    },    
    mounted() {
        this.getData()
    }

}

</script>

<style>


</style>