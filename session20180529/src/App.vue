<template>
  <div id="app" class="container">
    <Header title="More VueJS: Using vue-cli"/>
    
    <List :members="members" />  

    <NameInput />       
      
    <Footer :number="members.length"/>
  </div>
</template>

<script>

import Header from './components/Header.vue';
import List from './components/List.vue';
import NameInput from './components/NameInput.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'app',
  components: {
    Header,
    List,
    NameInput,
    Footer
  },
  data() {
    return {
      members: [
        {name:"Jack"},
        {name:"Jill"}
      ]
    };
  }
}
</script>

<style>

  body {
    background-color: #333;
    color: white;
  }

</style>
