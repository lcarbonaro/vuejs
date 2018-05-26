<template> 
  <div class="container">
    <input placeholder="Enter name to add" type="text" v-model="newName" v-on:keyup.enter="addName" /> 
  </div>  
</template>

<script>
export default {
  name: "NameInput",
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
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input {
  color: white;
}
</style>
