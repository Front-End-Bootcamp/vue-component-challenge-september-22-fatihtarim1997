<script setup>
import { onMounted, ref } from "vue";

import groupData from "./assets/data/data.json";

import Button from "./components/Button/Button.vue";
import Card from "./components/Card/Card.vue";

const groupNames = ref([]);
const students = ref([]);

function getGroupNames() {
  const groupNames = groupData.map((person) => person.group);
  const unuqueNames = [...new Set(groupNames)];
  return unuqueNames;
}

const getStudent = (name) => {
  let filterByGroupName = groupData.filter((person) => person.group === name);
  return filterByGroupName;
};

const filterByNameHandler = (name) => {
  const result = getStudent(name);
  students.value = result;
 
};

onMounted((name) => {
  groupNames.value = getGroupNames();
});
</script>
<template>
  <main class="main">
    <header class="header">
      <Button
        v-for="name in groupNames"
        :key="name"
        :name="name"
        @setName="filterByNameHandler"
      ></Button>
    </header>
    <div class="content">
      <Card :data="students"></Card>
    </div>
  </main>
</template>

<style scoped>
.main {
  width: 100%;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: stretch;
  justify-content: center;
}
.header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;

  min-height: 80px;
}
.content {
  margin: 40px;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: flex-start;
  justify-content: flex-start;
}
</style>
