// Post.vue

<template>
  <div class="home">
  <img alt="Vue logo" src="../assets/logo.png">
    <img v-if="post.fimg_url" class="img-fluid" :src=post.fimg_url>
    <img v-else class="img-fluid" src="https://picsum.photos/350/363">
    <div class="container">
      <div class="row">
        <div class="col-12">
            <h1 v-html="post.title.rendered"></h1>
            <div v-html="post.content.rendered"></div>
        </div>
      </div>
     </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'post',
  data(){
    return {
      post: []
    }
  },
    mounted(){
    axios.get('http://localhost/mariagraziabalducchi/wp-json/wp/v2/posts/' + this.$route.params.id)
    .then(response => {
      this.post = response.data
    })
    
  }
}
</script>