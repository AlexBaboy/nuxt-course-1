<template>
  <div>
    <h1>Обертка для страниц users</h1>
    <nuxt-child />
  </div>
</template>

<script>
export default {
  name: 'users',
  layout: 'default',
  middleware: 'checkAuth',
  created () {
    this.$log()
  }
}
</script>

<style scoped>

</style>
