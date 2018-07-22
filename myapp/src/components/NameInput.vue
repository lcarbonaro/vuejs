<template>

  <div>
    <input v-model="newName" type="text" @keyup.enter="addName" placeholder="Enter new name"/> 
    
  </div>
  
</template>

<script>
export default {
  name: 'Header',
  props: {
    
  },
  data() {
    return {
      newName: ''
    };
  },
  methods: {
    addName: function() {
      this.$parent.members.push({name: this.newName});
      this.newName = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

input {
  color:aquamarine;
}

</style>
