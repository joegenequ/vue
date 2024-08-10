<template>
  <h1>Food</h1>
  <p>Food items are generated with v-for from the 'foods' array.</p>
  <div id="wrapper">
    <food-item
      v-for="x in posts"  
      :key="x.id"
      :food-name="x.id"
      :food-desc="x.title"
      :is-favorite="x.favorite"/>
  </div>
</template>

<script>
import axios from 'axios'

  export default {
    data() {
      return {
        posts: []
      }
    },
    mounted() {
    axios
      .get('https://jsonplaceholder.typicode.com/posts/')
      .then((response) => {
        this.posts = response.data
      })
    }
  }




</script>

<style>
  #wrapper {
    display: flex;
    flex-wrap: wrap;
  }
  #wrapper > div {
    border: dashed black 1px;
    margin: 10px;
    padding: 10px;
    background-color: lightgreen;
  }
</style>