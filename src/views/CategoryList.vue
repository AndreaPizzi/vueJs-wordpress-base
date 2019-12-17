<template>
  <div class="home">
  <img alt="Vue logo" src="../assets/logo.png">
  <div>
    <div class="container">
      <div class="row">
       <Category 
      v-for="category in categories"
      v-bind:key="category.id"
      v-bind:category="category"/>
      </div>
      </div>
      </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Category from '@/components/Category.vue'
import axios from 'axios'

export default {
  name: 'categories',
  data(){
    return {
      categories: []
    }
  },
   components: {
    Category
  },
    mounted(){
    axios.get('http://localhost/mariagraziabalducchi/wp-json/wp/v2/categories?per_page=100' )
    .then(response => {
      this.categories = response.data
    })
    
  }
}
</script>