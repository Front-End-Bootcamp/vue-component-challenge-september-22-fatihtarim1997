<script setup>
import { onMounted, ref } from "vue";
import data from "./assets/svg/data/data.json";
import SelectBox from "./components/SelectBox.vue";
import PersonCard from "./components/PersonCard.vue";
import Test from "./components/test.vue";

const groupNames = ref([]);
const selectedGroup = ref();
const selectedPersonList = ref({});

groupNames.value = data;
// Seçilen grubun kişilerinin filtrelenmesi 
const selectGroup = (selectedGroup) => {
	data.forEach((person) => {
		if (person.group === selectedGroup.value) {
			selectedPersonList.value = [person];
		}
	});
};
</script>

<template>
	<div class="select_div">
		<SelectBox :groupNames="groupNames" @selectGroup="selectGroup" />
	</div>
	<hr />
	<div class="person_div">
		<PersonCard :selected="selectedPersonList"  />
	</div>
</template>

<style scoped>
.app_home {
	display: flex;
	justify-content: center;
	align-items: center;
}
.person_div {
	display: flex;
	flex-wrap: wrap;
}
</style>
