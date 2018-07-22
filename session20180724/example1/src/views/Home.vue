<template>
  <v-container>
    <v-layout row>
      <v-flex xs12 sm6 >
        <h3>News Headlines</h3>
      </v-flex>
    </v-layout>

    <v-layout row>
      <v-flex xs12 sm6 >
        <v-autocomplete        
          :items="selItems" 
          item-text="itemText"    
          item-value="itemVal"        
          label="Source"  
          v-model="selItem"       
          @change="onSelectItem()"              
        ></v-autocomplete>          
      </v-flex>
    </v-layout>

    <v-layout row wrap>
      <v-flex
        v-for="card in cards"
        v-bind="{ [`xs${4}`]: true }"
        :key="card.title"
      >

      <Card 
        :title="card.title" 
        :urlToImage="card.urlToImage" 
        :url="card.url" 
        :description="card.description" 
        @save-for-later="saveForLater(card)"/>

      </v-flex>
    </v-layout>

 </v-container>
</template>

<script>
import "isomorphic-fetch";
import Card from "../components/Card.vue";

const creds = require("../../creds.json"); // holds api key from newsapi.org

export default {
  name: 'home',
  components: {
    Card
  },

  data() {
    return {
      selItem: null,
      selItems: [],
      cards: []
    };
  },

  mounted() {
    fetch("https://newsapi.org/v2/sources?apiKey=" + creds.apiKey)
      .then(resp => resp.json())
      .then(respJson => {
        this.selItems = respJson.sources.map(s => {
          return { itemVal: s.id, itemText: s.name };
        });
      });
  },

  methods: {
    onSelectItem() {
      this.cards = [];
      fetch('https://newsapi.org/v2/top-headlines?sources=' + this.selItem + "&apiKey=" + creds.apiKey)
      .then(resp => resp.json())
      .then(respJson => {
        this.cards = respJson.articles;
      });
    },

    saveForLater(card) {
      //console.log('in Home saveForLater');
      this.$emit('save-article',card);
    }
  }

};
</script>
