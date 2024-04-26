<script>
export default {
	props: ['client'],
};
</script>

<template>
	<div>
		<img
			:src="client.img"
			:title="client.title"
			:alt="client.alt"
			class="w-40 py-3 px-5 border border-ternary-light dark:border-ternary-dark shadow-sm rounded-lg mb-8 cursor-pointer dark:bg-secondary-dark"
		/>
	</div>
</template>

<style lang="scss" scoped></style>
