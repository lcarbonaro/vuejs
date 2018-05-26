<template> 
  <div class="container">
    <footer>
      We currently have {{ number }} member(s).
    </footer>  
  </div>  
</template>

<script>
export default {
  name: "Footer",
  props: {
    number: Number
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
