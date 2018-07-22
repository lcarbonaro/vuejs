<template>
  <v-app>
    
    <Header :totalSaved="savedArticles.length" />

    <v-content>
      <v-container fluid>
        <router-view @save-article="saveArticle" :savedArticles="savedArticles"></router-view>
      </v-container>
    </v-content>

    <Footer />

  </v-app>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';

export default {
  components: {
    Header,
    Footer
  },
  data() {
    return {
      savedArticles:[]
    };
  },

  methods: {
    saveArticle(article) {
      //console.log('in App saveArticle');
      this.savedArticles.push(article);
    }
  }
  
}
</script>

<style>

</style>
