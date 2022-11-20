<template>
  <div class="home">
    <!-- <RestaurantRow toto="toto" /> -->
    <RestaurantRow
      v-for="(data, i) in dataRestaurant"
      :key="i"
      :threeRestaurant="data"
    />
  </div>
</template>

<script>
import Bdd from "../Bdd.js";
import { onMounted, ref } from "vue";
import RestaurantRow from "../components/RestaurantRow";
export default {
  name: "Home-hom",
  components: {
    RestaurantRow,
  },
  setup() {
    // console.log(Bdd);
    class Restaurant {
      constructor(name, note, image, drive_time) {
        this.name = name;
        this.note = note;
        this.image = image;
        this.drive_time = drive_time;
      }
    }
    // let resto = new Restaurant('toto', 4.5, 'img', '45min')
    // console.log(resto);

    let dataRestaurant = ref([]);

    const makeDataRestaurant = () => {
      let threeRestaurant = [];
      for (const restaurant of Bdd) {
        // console.log(restaurant);
        const newResaurant = new Restaurant(
          restaurant.name,
          restaurant.note,
          restaurant.image,
          restaurant.drive_time
        );
        if (threeRestaurant.length === 2) {
          threeRestaurant.push(newResaurant);
          dataRestaurant.value.push(threeRestaurant);
          threeRestaurant = [];
        } else {
          threeRestaurant.push(newResaurant);
        }
      }
      console.log(dataRestaurant);
    };
    // makeDataRestaurant();
    onMounted(makeDataRestaurant);
    //dernierer chiose du setup: return
    return {
      dataRestaurant,
    };
  },
};
</script>

<style>
</style>