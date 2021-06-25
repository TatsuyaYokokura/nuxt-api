<template>
  <div>
    <Header />
    <v-container>
      <ul v-for="post in posts" :key="post.id">
        <li>{{ post.title }}</li>
      </ul>
    </v-container>
    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get(
      'https://jsonplaceholder.typicode.com/posts'
    )
    return { posts }
  },
}
</script>

<style></style>
