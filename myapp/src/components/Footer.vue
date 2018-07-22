<template>

  <div>
    <br/>
    <p>We currently have {{ number }} member(s).</p>    
  </div>
  
</template>

<script>
export default {
  name: 'Header',
  props: {
    number: Number
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>


</style>
