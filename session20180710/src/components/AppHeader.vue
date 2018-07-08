<template>
  <v-toolbar color="light-blue">
    <v-toolbar-side-icon color="white"></v-toolbar-side-icon>
    <v-toolbar-title class="white--text">Mississauga Coding</v-toolbar-title>
    <v-spacer></v-spacer>
    <v-toolbar-items class="hidden-sm-and-down">
      <v-btn flat to="/" class="white--text">Home</v-btn>
      <v-btn flat to="/about" class="white--text">About</v-btn>
      <v-btn flat to="/contact" class="white--text">Contact</v-btn>
      <v-btn flat to="/pics" class="white--text">Images</v-btn>
    </v-toolbar-items>
  </v-toolbar>
</template>

<script>
export default {
    name: 'AppHeader'

}
</script>

<style>

</style>
