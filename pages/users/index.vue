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
import { mapGetters } from 'vuex'
export default {
  name: 'users',
  computed: {
    ...mapGetters({
      users: 'users/getUsers'
    })
  }
}
</script>

<style scoped>

</style>
