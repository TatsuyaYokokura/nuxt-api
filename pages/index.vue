<template>
  <div>
    <Header />
    <v-container>
      <v-row>
        <PostsList v-for="post in posts" :key="post.id" :post="post" />
      </v-row>
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
