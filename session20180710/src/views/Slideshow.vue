<template>

  <v-carousel>
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>

</template>

<script>
export default {
    name: 'Slideshow',
    data () {
      return {
        items: [
          {
            src: 'https://picsum.photos/1440/500/?image=123'
          },
          {
            src: 'https://picsum.photos/1440/500/?image=456'
          },
          {
            src: 'https://picsum.photos/1440/500/?image=789'
          },
          {
            src: 'https://picsum.photos/1440/500/?image=012'
          }
        ]
      }
    }
  }
</script>

<style>

</style>
