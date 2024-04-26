<script>
export default {
	props: ['project'],
};
</script>

<template>
	<a
		:key="project.id"
		:href="project.url"
		target="__blank"
		class="rounded-xl shadow-lg hover:shadow-2xl cursor-pointer mb-10 sm:mb-0 bg-secondary-light dark:bg-ternary-dark"
	>
		<div>
			<img
				:src="project.img"
				:alt="project.title"
				class="rounded-t-xl border-none"
			/>
		</div>
		<div class="text-center px-3 py-4">
			<p
				class="font-general-semibold text-xl text-ternary-dark dark:text-ternary-light font-semibold mb-2 hover:text-indigo-600  dark:hover:text-indigo-400"
			>
				{{ project.title }}
			</p>
			<span
				class="font-general-light text-base text-ternary-dark dark:text-ternary-light"
				>{{ project.category }}</span
			>
		</div>
	</a>
</template>

<style lang="scss" scoped></style>
