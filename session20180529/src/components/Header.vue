<template>
  
      <div class="container">
        <p>
          {{ title }}
        </p>
        <hr/>
      </div>    
  
</template>

<script>
export default {
  name: "Header",
  props: {
    title: String    
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
