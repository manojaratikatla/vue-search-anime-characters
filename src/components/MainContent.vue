<template>
    <v-card class="mx-auto">
        <v-container>
            <v-row dense>
                <v-col v-for="(item, i) in items" :key="i" cols="12">
                    <v-card elevation="6">
                        <div class="d-flex flex-no-wrap">
                            <v-avatar class="ma-3" size="36" height="auto" tile>
                                <v-img :src="item.src"></v-img>
                            </v-avatar>
                            <div>
                                <v-card-title class="text-h5" v-text="item.title"></v-card-title>

                                <v-card-subtitle v-text="item.artist"></v-card-subtitle>

                            </div>
                            <div class="d-flex justify-center align-center ma-3" size="36">
                                <v-btn>
                                    <v-icon left>
                                        mdi-arrow-right-bold
                                    </v-icon>
                                </v-btn>
                            </div>
                        </div>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
        <div class="pagination">
            <v-pagination v-model="page" :length="6"></v-pagination>
        </div>
    </v-card>
</template>

<script>
import axios from 'axios';
export default {
    name: 'MainContent',
    data: () => ({
        items: [
            {
                color: '#1F7087',
                src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
                title: 'Supermodel',
                artist: 'Foster the People',
            },
            {
                color: '#952175',
                src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
                title: 'Halcyon Days',
                artist: 'Ellie Goulding',
            },
        ],
        animeCharacters: [],
        page: 1,
    }),
    methods: {
        getAnimeCharacter() {
            axios.get('https://api.jikan.moe/v4/characters?page=0&limit=15&q=&order_by=favorites&sort=desc')
                .then((response) => {
                    console.log(response.data)
                    this.animeList = response.data
                })
                .catch((error) => {
                    console.log(error)
                })
        }
    }
}
</script>