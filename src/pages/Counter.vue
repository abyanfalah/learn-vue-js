<script setup>
import { ref } from 'vue';

	const count = ref(0)
</script>

<template>
	<button @click="count++"><h4>Add</h4></button>
	<button @click="count > 0 ? count-- : null"><h4>Subtract</h4></button>
	<h1>{{ count }}</h1>
</template>