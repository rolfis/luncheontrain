<template>
  <div class="menu">
    <div>{{ menu.menuDate }}</div>
    <div :key="category.id" v-for="category in menu.recipeCategories">
      <h3>{{category.name}}</h3>
      <p>
        {{category.recipes[0].displayNames[0].displayName}}
      </p>
    </div>
    
  </div>
</template>

<script>
import axios from 'axios'

export default {
  props: {
    restaurant: Object
  },
  name: 'Menu',
  data: function () {
    return {
      menu: {}
    };
  },
  mounted() {
    axios.get(this.restaurant.url).then(response => {
      this.menu = response.data
    })
  }
}
</script>
