<template>
  <v-col cols="6">
    <v-card height="100%">
      <v-card-title>{{ cardTitle }}</v-card-title>
      <v-list>
        <v-list-item
            v-for="item in items"
            :key="item.title"
        >
          <v-list-item-icon>
            <v-icon :color="item.color">{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
          <v-list-item-icon class="mr-16">
            <v-icon>{{item.star}}</v-icon>
          </v-list-item-icon>
        </v-list-item>
      </v-list>
    </v-card>
  </v-col>
</template>

<script>
export default {
  name: "LayoutCard",
  props: ["items", "cardTitle"]
}
</script>

<style scoped>

</style>