<template>
    <div>
      <Html
        :lang="'en-US'"
      >
        <Head>
          <Title>Restaurant review app</Title>
          <Meta 
          name="description"
          content="Application about top 50 restaurants in the world"
        />  
      </Head>
      </Html>
      <div class="container">
        <h1>Welcome to Restorant review!</h1>
        <NuxtLink to="/restaurants">Go to restaurants page</NuxtLink>
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