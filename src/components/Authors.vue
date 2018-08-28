<template>
    <div>
        <Header />
        <p>
            Hooray for authors! 
        </p>

    </div>   

</template>


<script>
import Header from './Header'

export default {
    name: "Authorslist",
    components: {
        Header
    },
    data(){
        return {
            authors: null
        }
    }//,
    // methods: {
    //     getData(){
    //         fetch('http://localhost:9000/authors')
    //         .then(response => {
    //             console.log("the response from authors fetch: ", response);
    //             return response.json();
    //         })
    //         .then( json => {
    //             this.authors = json.authors;
    //             console.log("here's what's in my data object for authors: ", this.authors);
    //         });
    //     }
    // },    
    // mounted() {
    //     this.getData()
    // }

}

</script>

<style>


</style>