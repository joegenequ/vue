<template>
  <div>
    <h2>
      {{ foodName }}
      <img src="/img_quality.svg" v-show="foodIsFavorite">
    </h2>
    <p>{{ foodDesc }}</p>
    <button v-on:click="toggleFavorite">Favorite</button>
  </div>
</template>

<script>
  import axios from 'axios'
  export default {
        props: {
           foodName: {
                type: Number,
                required: true
            },
           foodDesc: {
             type: String,
             required: false,
             default: 'This is the default description.'
             
           },
           isFavorite: {
             type: Boolean,
             required: false,
             default: false
             }
        },
        data() {
          return {
            foodIsFavorite: this.isFavorite
          }
        },
        methods: {
          toggleFavorite() {
            this.foodIsFavorite = !this.foodIsFavorite;
          }
        }           
    }
</script>

<style>
  img {
    height: 1.5em;
    float: right;
  }
</style>