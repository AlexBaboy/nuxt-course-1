<template>
  <div>
    <h1>Пользователи</h1>
    <ul>
      <li
        v-for="user in users"
        :key="user.id"
      >
        <nuxt-link :to="`users/${user.id}`">{{ user.name }}</nuxt-link>
      </li>
    </ul>
    <nuxt-link to="/users/1">Перейти к пользователю</nuxt-link>
  </div>
</template>

<script>

export default {
  name: 'users',
  async asyncData () {
    const response = await fetch('https://jsonplaceholder.typicode.com/users')
    const users = await response.json()

    return {
      users
    }
  },
  data () {
    return {
      users: []
    }
  }
}
</script>

<style scoped>

</style>
