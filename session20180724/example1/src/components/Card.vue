<template>
  <v-card class="mr-4 mb-4">

    <v-card-media :src="urlToImage" height="200px" >
      <v-container fill-height fluid pa-2>
        <v-layout fill-height>
          <v-flex xs12 align-end flexbox>
            <span class="headline white--text" v-text="title"></span>
          </v-flex>
        </v-layout>
      </v-container>
    </v-card-media>

    <v-scale-transition>
      <v-card-title primary-title v-show="showDesc">          
        <div v-text="description"></div>          
      </v-card-title>
    </v-scale-transition>

    <v-card-actions>          
      <v-btn flat color="orange" @click="onClickReadMore(url)">Read More</v-btn>
      <v-btn flat color="orange" @click="onClickSave(title,url,urlToImage,description)">Save For Later</v-btn>
      <v-spacer></v-spacer>
      <v-btn icon @click="showDesc = !showDesc">
        <v-icon>{{ showDesc ? 'keyboard_arrow_up' : 'keyboard_arrow_down' }}</v-icon>
      </v-btn>
    </v-card-actions>
    
  </v-card>           
</template>

<script>
export default {
  name: "Card",
  props: {
    title: String,
    url: String,
    urlToImage: String,
    description: String
  },
  data() {
      return {
          showDesc: false
      };
  },
  methods: {
      onClickReadMore(link) {
          window.open(link);
      },

      onClickSave(title,link,image,desc) {
          //console.log('in Card onClickSave');
          this.$emit('save-for-later',{
              title: title,
              url: link,
              urlToImage: image,
              description: desc
          });

      }
  }
};
</script>

<style>
</style>
