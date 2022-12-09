<script setup>
import Home from './pages/Home.vue'
import Counter from './pages/Counter.vue'
import Write from './pages/Write.vue'
import About from './pages/About.vue'
import { reactive, ref } from 'vue';

let currentPage = ref('Home')

const pages = {
	Home,
	Counter,
	Write,
	About
}

</script>

<template>
	<main>
		<h3>{{ currentPage }}</h3>
		<button
			v-for="(_, page) in pages"
			@click="currentPage = page"
		>{{ page }}</button>
		<hr/>

		<KeepAlive>
			<component :is="pages[currentPage]"></component>
		</KeepAlive>
	</main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
