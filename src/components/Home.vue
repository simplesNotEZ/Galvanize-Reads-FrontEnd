<template>
    <div class="homeDiv">
        <Header />
        <main>
            <section>
                <router-link class="authors" to="/authors">
                    <img src="https://via.placeholder.com/625x450" class="image" alt="some authors" />
                    <h2>Authors</h2>
                </router-link>
            </section>
            <section>
                <router-link class="books" to="/books">
                    <img src="https://via.placeholder.com/625x450" class="image" alt="some books" />
                    <h2>Books</h2>
                </router-link>
            </section>
        </main>
    </div>


</template>

<script>
import Header from './Header'

export default {
    name: 'Home',
    components: {
        Header
    }
    
}


</script>


<style scoped>

.homeDiv {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin: 0;
    padding: 0;
}

main {
    display: flex;
}
section {
    border: .125vw solid black;
    width: 50vw;
}
.image {
    padding: 2vw;
}
a {
    text-decoration: none;
    color: black;
}


</style>