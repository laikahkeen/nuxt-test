<template>
	<div>
		<h2>About</h2>
		<p>
			Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ullam eius
			vitae quae eveniet expedita quod voluptatibus pariatur. Est quas
			eaque odio laudantium earum ipsam maiores, dolore tenetur numquam
			mollitia? Aut.
		</p>
		<p>
			{{ data }}
		</p>
	</div>
</template>

<script setup>
const { data } = await useFetch("/api/currency/MYR");
</script>

<style scoped></style>
