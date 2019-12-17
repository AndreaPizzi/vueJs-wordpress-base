<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="container">
  <div class="row">
    <PostSmall 
      v-for="post in posts"
      v-bind:key="post.id"
      v-bind:post="post"/>
      </div>
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
import PostSmall from '@/components/PostSmall.vue'

export default {
  name: 'home',
  data(){
    return {
      posts: []
    }
  },
  components: {
    PostSmall
  },
    mounted(){
    axios.get('http://localhost/mariagraziabalducchi/wp-json/wp/v2/posts/')
      .then((r) => this.posts = r.data);
  }
}
</script>
