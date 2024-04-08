<template>
  <div>
    <h1>{{ home.title }}</h1>
    <p>{{ home.description }}</p>
  </div>
</template>

<template>
  <div>
    <h1>Products</h1>
    <ul>
      <li v-for="product in products" :key="product.name">
        <h2>{{ product.name }}</h2>
        <p>Description: {{ product.description }}</p>
        <p>Price: {{ product.price }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const yamlData = await $axios.$get('/products.yml');
    const products = yamlData || [];
    return { products };
  }
}
</script>

<style scoped>
/* Add your page styles here */
</style>