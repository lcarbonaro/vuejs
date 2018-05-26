<template> 
  <ul class="container">
    <li v-for="(m,i) in members" :key="i" >
      <button class="btn-small blue" v-on:click="deleteItem(i)">Del</button>&nbsp;
      {{ m.name }}       
    </li>
  </ul>
</template>

<script>
export default {
  name: "ListItem",
  props: {
    members: Array
  },
  methods: {
    deleteItem: function(i) {
      this.members.splice(i,1);
    }

  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  button {
    margin: 2px 0 2px 0;
  }
</style>
