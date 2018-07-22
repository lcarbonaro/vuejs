<template>

<ul>
  <li v-for="(n,index) in names" :key="index" >
    <button class="btn-small blue" v-on:click="deleteName(index)">Del</button>
    {{n.name}}
  </li>
</ul>
  
  
</template>

<script>
export default {
  name: 'List',
  props: {
   names: Array
  },
  methods: {
    deleteName: function(i) {
      this.names.splice(i,1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  margin: 2px 0 2px 0;
}


</style>
