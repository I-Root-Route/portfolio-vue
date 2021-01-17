<template>
  <v-col cols="4">
    <v-card
        class="mt-4"
        height="100%"
    >
      <v-img
          class="white--text align-end"
          height="200px"
          :src=cardImage
      >
        <v-card-title class="white--text" style="font-weight: bold">{{ Title }}</v-card-title>
      </v-img>


      <slot></slot>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn
            color="orange"
            text
            :href="linkto"
        >
          サイトページ
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: "LayoutWorkCard",
  props: ["cardImage", "Title", "linkto"]
}
</script>

<style scoped>

</style>