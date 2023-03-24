<template>
    <Html
        :lang="'en-US'"
      >
        <Head>
          <Title>Top 50 restaurants in the world</Title>
          <Meta 
          name="description"
          content="Application about top 50 restaurants in the world"
          />
        </Head>
      </Html>
    <div>
        <NuxtLayout name="custom">
            <div class="container">
                <RestaurantsTable />
            </div>
        </NuxtLayout>
    </div>
</template>

<script setup lang="ts">



</script>

<style scoped>

</style>