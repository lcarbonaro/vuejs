<template>
  <v-app>
    <AppHeader/>
    <v-container>
      <router-view></router-view>
    </v-container>  
    <AppFooter/>
  </v-app>
</template>


<script>
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  components: {
    AppHeader,
    AppFooter
  } 
};
</script>
