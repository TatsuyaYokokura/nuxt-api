<template>
  <v-container>
    <v-btn @click="getUsers">getUsers(data)</v-btn>
    <v-btn @click="getAllUsers">getUsers(all)</v-btn>
  </v-container>
</template>

<script>
export default {
  methods: {
    async getUsers() {
      const users = await this.$axios.$get(
        'https://jsonplaceholder.typicode.com/users'
      )
      // eslint-disable-next-line no-console
      console.log(users)
    },
    async getAllUsers() {
      const users = await this.$axios.get(
        'https://jsonplaceholder.typicode.com/users'
      )
      // eslint-disable-next-line no-console
      console.log(users)
    },
  },
}
</script>

<style></style>
