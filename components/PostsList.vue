<template>
  <v-col cols="4">
    <v-card>
      <v-list-item three-line>
        <v-list-item-content>
          <div class="text-overline mb-4">OVERLINE</div>
          <v-list-item-title class="text-h5 mb-1">
            {{ post.title }}
          </v-list-item-title>
          <v-list-item-subtitle>
            {{ post.body }}
          </v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
      </v-list-item>

      <v-card-actions>
        <v-btn outlined rounded text> Button </v-btn>
      </v-card-actions>
    </v-card>
  </v-col>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
}
</script>
