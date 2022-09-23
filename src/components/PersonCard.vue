<script setup>
const props = defineProps(["selected"]);
console.log(props.selected);
const selectedPersonList=props.selected;
</script>
<template>
	<div v-for="person in selectedPersonList" class="person_body">
		<p class="person_name">{{person.name}}</p>
		|
		<p class="person_type">Type:Student</p>
	</div>
</template>
<style>
.person_body {
	background-color: aliceblue;
	display: flex;
	justify-content: center;
	align-items: center;
	padding: 10px;
	width: 200px;
	height: 200px;
	border-radius: 20px;
	box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
		rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
	margin: 10px 10px;
}
</style>
