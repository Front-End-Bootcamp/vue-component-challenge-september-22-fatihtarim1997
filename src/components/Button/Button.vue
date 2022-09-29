<script setup>
const props = defineProps(["name"]);
const emit = defineEmits(['setName']);

const nameHandler = name =>{
    emit('setName',name)
}
</script>
<template>
  <button class="button" :class="name.toLowerCase()" @click="nameHandler(props.name)">{{ props.name }}</button>
</template>

<style scoped>
.button {
    
  background-color: aliceblue;
  border: 1px solid #222222;
  border-radius: 8px;
  color: #222222;
  cursor: pointer;
  display: inline-block;
  font-size: 16px;
  font-weight: 600;
  line-height: 20px;
  margin: 5px 5px;
  outline: none;
  padding: 13px 23px;
  position: relative;
  text-align: center;
  width: auto;
}
.orchid {
  background-color: orchid;
}

.steelblue {
  background-color: steelblue;
}

.indianred {
  background-color: indianred;
}

.yellowgreen {
  background-color: yellowgreen;
}

.lightseagreen {
  background-color: lightseagreen;
}

</style>
