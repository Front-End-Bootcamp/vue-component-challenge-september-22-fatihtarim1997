<script setup>
import { ref } from "vue";

const props = defineProps(["groupNames"]);
const emits = defineEmits(["selectGroup"]);
// 
const groups = props.groupNames;
const uniqueGroup = groups.map((group) => group.group);
const uniqueGroups = [...new Set(uniqueGroup)];

const selectedGroup = ref("");

const getGroup = () => {
	emits("selectGroup", selectedGroup);
};
</script>

<template>
	<select v-model="selectedGroup" class="group_select">
		<option v-for="group in uniqueGroups">{{ group }}</option>
	</select>
	<button @click="getGroup">Seç</button>
</template>

<style>
.group_select {
	width: 200px;
	height: 30px;
}
</style>
