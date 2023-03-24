<template>
    <div class="table">
      <h1>TOP 50: THE RANKING</h1>
      <div class="table-container">
        <div class="table-col">
            <RestaurantsRow :isHeader="true"/>
            
            <RestaurantsRow 
            v-for="(restaurant, index) in restaurantsOrganized.first"
            :key="restaurant.id"
            :name="restaurant.name"
            :rank="restaurant.rank"
            :index="index"
            />
        </div>
        <div class="table-col">
            <RestaurantsRow :isHeader="true"/>
            <RestaurantsRow 
            v-for="(restaurant, index) in restaurantsOrganized.second"
            :key="restaurant.id"
            :name="restaurant.name"
            :rank="restaurant.rank"
            :index="index"
            />
        </div>
      </div>
    </div>
</template>
<script setup lang="ts">
import restauantsData from "@/data.json";

const restaurantsOrganized = {
    first: [...restauantsData].slice(0, 25),
    second: [...restauantsData].slice(25)
}
</script>
  <style scoped>
  .table {
    margin: 3rem 0;
  }
  .table h1 {
    margin-bottom: 2rem;
  }
  .table-container {
    display: flex;
    justify-content: space-between;
  }
  .table-col {
    width: 48%;
  }
  </style>