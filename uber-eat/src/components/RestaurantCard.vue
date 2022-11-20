<template>
  <div  class="retaurant--card">
    <div :style="changeBackground" class="restaurant--image">
        <!-- <img v-bind:src="infoRestaurant.image " alt=""> -->
    </div>
    <div class="restaurant--information">
      <div class="top">
        <p class="name">
            {{ infoRestaurant.name }}
        </p>
        <p class="note">
            <span>
                 {{ infoRestaurant.note }}
                </span>
                 </p>
      </div>
      <p class="time">
        {{ infoRestaurant.drive_time }}
      </p>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue';
export default {
    name: "RestaurantCard",
    props: {
        infoRestaurant: Object
    },
    setup(props) {
        console.log(props.infoRestaurant);
        const changeBackground= computed(()=> {
            return {
                backgroundImage: `url(${props.infoRestaurant.image})`
            }
        })
        return {
            changeBackground
        }
    }
};
</script>

<style lang="scss">
.retaurant--card {
  width: 32%;
  height: 30vh;

  .restaurant--image {
    background-image: url("https://cn-geo1.uber.com/image-proc/resize/eats/format=webp/width=550/height=440/quality=70/srcb64=aHR0cHM6Ly9kMXJhbHNvZ25qbmczNy5jbG91ZGZyb250Lm5ldC8zNzg4MDJiMC1jNTI4LTQ4MjktYjBiNS0wY2M2NDBkZjYzY2QuanBlZw==");
    height: 70%;
    background-position: center;
    background-size: cover;
  }

  .restaurant--information {
      .top{
        margin: 10px 0px;

        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .note{
background-color: #eeee;
height: 30px;
width: 30px;
display: flex;
justify-content: center;
align-items: center;
font-size: 0,8rem;
border-radius: 50%;
    }

    .time {
        font-size: 0,9rem;

    }
  }
}
</style>