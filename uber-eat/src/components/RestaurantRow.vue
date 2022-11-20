<template>
  <div class="restaurant--row">
 <h2 classe="title">
    Nos Restaurants
    <!-- {{ toto }} -->
 </h2>
 
 <div class="wrapper--card">
    <RestaurantCard v-for="(card , index) in threeRestaurant" :infoRestaurant="card" :key="index"/>
    </div>
  </div>
</template>

<script>
    import RestaurantCard from './RestaurantCard.vue'
export default {
    name: "ReastaurantRow",
    components: {
        RestaurantCard,
    },
    props: {
        // toto: String
        threeRestaurant: Array
    }
}
</script>

<style lang="scss">
.restaurant--row {
    .wrapper--card {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
}

</style>