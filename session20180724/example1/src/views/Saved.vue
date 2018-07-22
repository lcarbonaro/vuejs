<template>  
  <v-container>
      
    <v-layout row>
      <v-flex xs12 sm6 >
        <h3>Saved Articles</h3>
      </v-flex>
    </v-layout>

    <v-list>
      <v-list-tile
        v-for="(a,i) in savedArticles" 
        :key="i"
        avatar
        @click="onClickSavedArticle(a.url)" >
            
        <v-list-tile-avatar>
          <img :src="a.urlToImage">
        </v-list-tile-avatar>

        <v-list-tile-content>
          <v-list-tile-title v-text="a.title"></v-list-tile-title>
        </v-list-tile-content>

      </v-list-tile>
    </v-list>

  </v-container>
</template>

<script>
export default {
    name: 'saved',
    props: {
        savedArticles: Array
    },

    methods: {
        onClickSavedArticle(link) {
            window.open(link);
        }
    }

}
</script>

<style>

</style>
