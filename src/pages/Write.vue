<script setup>
import { reactive, ref } from 'vue';

const personName = ref('world')
</script>

<template>
	<label>
		<input v-model="personName" type="text" placeholder="type your name here">
	</label>

	<h3>Hello {{ personName }} !</h3>
</template>