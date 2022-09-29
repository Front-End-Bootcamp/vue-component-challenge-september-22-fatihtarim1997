<script setup>
import CardItem from "./CardItem.vue";

const props = defineProps(["data"]);
</script>

<template>
  <CardItem v-for="item in props.data" :key="item" :item="item"></CardItem>
</template>

<style scoped>
.card {
  margin: 20px;
  display: flex;
  flex-wrap: wrap;
  background-color: aliceblue;
  color: rgb(37, 37, 37);
}
</style>
