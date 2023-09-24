<template>
	<div>
		<Head>
			<Title>Nuxt | {{ product.title }}</Title>
			<Meta name="description" :content="product.description"></Meta>
		</Head>
		<ProductDetails :product="product" />
	</div>
</template>

<script setup>
definePageMeta({
	layout: "products",
});

const a = ref("haha");
const { id } = useRoute().params;
const uri = "https://fakestoreapi.com/products/" + id;

const { data: product } = await useFetch(uri, { key: id });

if (!product.value) {
	throw createError({
		statusCode: 404,
		statusMessage: "Product not found",
		fatal: true,
	});
}
</script>

<style scoped></style>
