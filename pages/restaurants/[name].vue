<template>
    <div>
      <NuxtLayout name="custom" v-if="restaurant">
        <div  class="restaurant-container">
        <div class="image-container">
            <img :src="restaurant?.imageUrl" alt="restaurant?.name" />
        </div>
        <div class="info-container">
            <h1>{{ restaurant?.name }}</h1>
            <div class="stats-container">
            <h5>Revenue (in billions)</h5>
            <p>${{ restaurant?.revenue }}</p>
            </div>
            <div class="stats-container">
            <h5>Number of Stores</h5>
            <p>{{ restaurant?.numberOfStores }}</p>
            </div>
            <p class="content">{{ restaurant?.content }}</p>
        </div>
        </div>
      </NuxtLayout>
      <div  class="restaurant-not-found" v-else>
        <NuxtLayout name="error" >
            <template #header><h1>Page not found</h1></template>
            <template #btn>
              <button  
                class="btn btn-primary btn-lg"
                @click="$router.push('/restaurants')"
              >Go back</button>
          </template>
        </NuxtLayout>
      </div>
    </div>
</template>
  
<script setup lang="ts">
import restaurants from '@/data.json';



const route = useRoute();
const name = route.params.name;

const restaurant = restaurants.find( r => r.name === name);

useHead({
  title: restaurant ? restaurant.name : "404 - Restaurant not found",
  meta: [
    {
      name: 'description',
      content: restaurant ? `${restaurant.name} such a good place to visit!` : ""
    }
  ]
})
</script>


<style scoped>
  .restaurant-container {
    display: flex;
  }
  .image-container {
    width: 70%;
    height: 100%;
  }
  .image-container img {
    width: 100%;
    height: 100%;
  }
  .restaurant-not-found {
    height: 75vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .restaurant-not-found h1 {
    margin-bottom: 3rem;
  }
  .info-container {
    padding: 3rem;
    width: 50%;
  }
  .info-container h1 {
    text-transform: uppercase;
    font-size: 3rem;
    margin-bottom: 3rem;
  }
  .stats-container {
    display: flex;
    align-items: flex-end;
    margin-bottom: 1rem;
  }
  .stats-container h5 {
    width: 20rem;
    font-size: 2rem;
    margin: 0;
    margin-right: 5rem;
  }
  .stats-container p {
    font-size: 2rem;
    margin: 0;
  }
  .content {
    font-size: 1rem;
    margin-top: 2rem;
  }
  </style>