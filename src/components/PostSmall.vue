// PostSmall.vue
<template>
  <div class="col-4">
    <img v-if="post.fimg_url" class="img-fluid" :src=post.fimg_url>
    <img v-else class="img-fluid" src="https://picsum.photos/350/363">
    <div class="container">
        <div class="row">
            <div class="col-12">
                <h1 v-html="post.title.rendered"></h1>
                <div v-html="post.excerpt.rendered"></div>
                <router-link class="btn btn-success" v-bind:to="'/post/' + post.id">View more</router-link>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
  name: 'PostSmall',
  props: ['post']
}
</script>

<style scoped="">
h1 {
  margin: 40px 0 0;
}
</style>