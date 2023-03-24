<template>
    <div>
      <Nav />
      <div class="container">
        <NuxtLayout name="error">
          <template v-slot:header><h1>Page not found</h1></template>  
            <template v-slot:btn><NuxtLink to="/restaurants">Go to restaurants page</NuxtLink></template>
        </NuxtLayout>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  
  </script>
  
  <style scoped>
  .container {
    text-align: center;
    margin-top: 5rem;
  }
  </style>