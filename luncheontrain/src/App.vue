<template>
  <div>
    <NavBar></NavBar>
    <div><img src="/images/lunchtaget.svg" width="250" class="d-inline-block align-top" /></div>
    <div class="row">
    <div :key="restaurant.id" v-for="restaurant in restaurants">
      <div class="card">
        <div class="card-body">
          <h5>{{ restaurant.name }}</h5>
          <Menu :restaurant="restaurant"></Menu>
          <a :href="restaurant.url">Till hemsidan</a>
        </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
import NavBar from './components/NavBar'
import Menu from './components/Menu'

export default {
  components: {
    NavBar,
    Menu
  },
  name: 'app',
  data: function () {
    return {
    restaurants: [
      {
        id: 1,
        name: 'Kåren',
        url: 'https://carboncloudrestaurantapi.azurewebsites.net/api/menuscreen/getdataday?restaurantid=5'
      },
      {
        id: 2,
        name: 'Linsen',
        url: 'https://carboncloudrestaurantapi.azurewebsites.net/api/menuscreen/getdataday?restaurantid=33'
      },
      {
        id: 3,
        name: 'Express',
        url: 'https://carboncloudrestaurantapi.azurewebsites.net/api/menuscreen/getdataday?restaurantid=7'
      },
      {
        id: 4,
        name: 'S.M.A.K.',
        url: 'https://carboncloudrestaurantapi.azurewebsites.net/api/menuscreen/getdataday?restaurantid=42'
      }
    ]
  }}
}
</script>

<style scoped>
.card {
  width: 18rem;
}
</style>
