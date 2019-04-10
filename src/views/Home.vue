<template>
  <div class="home">
    <h1> All Posts </h1>
    <div v-for="post in posts">
      {{ post.title }}
      {{ post.body }}
    <img v-bind:src="image">
    <hr>
    </div>
  </div>
</template>

<style>
</style>

<script>

import axios from "axios";

export default {
  data: function() {
    return {
      posts: []
    };
  },
  created: function() {
    axios.get("/api/posts").then(response => {
      this.posts = response.data;
    });
  },
  methods: {}
};
</script>
