<template>
  <div id="app">
    <h1>All the posts</h1>
    <div v-for="post in posts">
      <h2> {{post.title}} </h2>
      <small> <em>{{post.date}}</em> </small>
      <p> {{post.body}} </p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      posts: []
    }
  },
  created () {
    fetch('/posts.json')
    .then(res => res.json())
    .then(data => {
      this.posts = data
      console.log(data)
    })
  }
}
</script>

<style>

body{
  max-width: 680px;
  margin: 0 auto;
}
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  border:1px solid gray;
  padding: 10px;
}

h1{
  border-bottom: 2px black solid;
  padding-bottom: 10px;
}

</style>
