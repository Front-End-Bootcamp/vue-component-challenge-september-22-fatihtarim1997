<script setup>
const props = defineProps(["item"]);
</script>

<template>
  <div class="card__item"  :class="{ '-assitant': props.item.type }">
    Name: {{ props.item.name }}
  </div>
</template>
<style>
.card__item {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 20px;
  padding: 10px;
  width: 150px;
  height: 150px;
  border-radius: 15px;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px,
    rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
}

.card__item.-assitant {
  order: -1;
  background: black;
  color: white;
}
</style>
