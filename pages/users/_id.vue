<template>
  <h1>Пользователь {{id}}</h1>
</template>

<script>
export default {
  name: '_id',
  validate ({ params }) {
    // Must be a number
    return /^\d+$/.test(params.id)
  },
  computed: {
    id () {
      return this.$route.params.id
    }
  }

}
</script>

<style scoped>

</style>
