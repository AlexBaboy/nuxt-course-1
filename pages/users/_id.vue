<template>
  <div v-if="user" class="user">
    <h1>{{ `Пользователь ${user.name}` }}</h1>
  </div>
</template>

<script>
export default {
  name: '_id',
  data () {
    return {
      user: null
    }
  },
  validate ({ params }) {
    // Must be a number
    return /^\d+$/.test(params.id)
  },
  async asyncData ({ params }) {
    const response = await fetch(`https://jsonplaceholder.typicode.com/users/${params.id}`)
    const user = await response.json()

    return {
      user
    }
  }
}
</script>

<style scoped>

</style>
