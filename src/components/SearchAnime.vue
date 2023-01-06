<template>
    <v-container>
        <header>
            <h1 class="Header">
                Search anime character
            </h1>
            <div class="search-box-content">
                <div class="search-input-field">
                    <v-text-field v-model="searchAnime" hide-details="auto" outlined rounded
                        prepend-inner-icon="mdi-magnify"></v-text-field>
                </div>
                <div class="search-button">
                    <v-btn class="d-flex align-center" x-large color="#8e7cc3" rounded>Search</v-btn>
                </div>
            </div>
            <div class="para">
                <p>Total ... matching anime characters found</p>
            </div>
        </header>
        <!-- <main class="main-content">
            <div class="display-content-container">
               
            </div>
        </main>  -->
    </v-container>
</template>

<script >
export default {
    name: 'SearchAnime',
    created() {
        this.getAnimeCharacters()
    },
    data() {
        return {
            // animeList: [],
            // hasError: false,
            // searchAnime: ''
        }
    },
    // methods: {
    //     getAnimeCharacters() {
    //         axios.get('https://api.jikan.moe/v4/characters?page=0&limit=15&q=&order_by=favorites&sort=desc')
    //             .then((response) => {
    //                 console.log(response.data)
    //                 this.animeList = response.data
    //             })
    //             .catch((error) => {
    //                 console.log(error)
    //             })
    //     }
    // }
}
</script>

<style scoped>
* {
    box-sizing: border-box;
    margin: 0;
    max-width: 100%;
}

.Header {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 50px;
    font-family: 'Roboto', sans-serif;
    Font-size: 48px;
    Font-weight: 400;
}

.footer {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #42A5F5;
    height: 48px;
}

.para{
    display: flex;
    justify-content: center;
    align-items: center;
}
.search-box-content {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
    padding: 20px;
}
.search-input-field {
    width: 600px;
}

</style>