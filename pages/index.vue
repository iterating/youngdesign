<template>
  <div>
    <h1>{{ homepage.title }}</h1>
    <p>{{ homepage.description }}</p>
  </div>
</template>

<script>
export default {
  async asyncData({ $content }) {
    // Load and parse the YAML file using YAML loader
    const homepageData = await import('!!yaml-loader!~/static/home.yml')
    return { homepage: homepageData.default }
  }
}
</script>

<style scoped>
/* Add your page styles here */
</style>