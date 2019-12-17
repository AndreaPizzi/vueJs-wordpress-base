<template>
  
        <div class="col-4">
          <h1 v-html="category.name"></h1>
          <router-link class="btn btn-success" v-bind:to="'/category/' + category.id">View more</router-link>
        </div>

</template>

<script>
export default {
  name: 'Category',
  props: ['category']
}
</script>

<style scoped>
h1 {
  margin: 40px 0 0;
}
</style>