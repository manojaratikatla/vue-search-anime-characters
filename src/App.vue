<template>
  <v-app>
    <v-main>
      <SearchAnime />
      <MainContent />
    </v-main>
  </v-app>
</template>

<script>
import SearchAnime from './components/SearchAnime.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    SearchAnime,
    MainContent
  },

  data: () => ({
    //
  }),
};
</script>
