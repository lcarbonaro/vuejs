<template>
  <div id="app" class="container">
    <Header title="More VueJS: Using vue-cli" /> 
    <List v-bind:names="members" />  

    <NameInput />

    <Footer :number="members.length" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import List   from './components/List.vue'
import Footer from './components/Footer.vue'
import NameInput from './components/NameInput.vue'

export default {
  name: 'app',
  components: {
    Header,
    List,
    Footer,
    NameInput
  },
  data() {
    return {
      members: [
        {name:'Jack'},
        {name:'Jill'},
        {name:'Wilma'}
      ]
    };
  }
}
</script>

<style>
body {
  background-color: #333;
  color:white;
}
</style>
