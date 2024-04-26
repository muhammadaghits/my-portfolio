<script>
import ThemeSwitcher from '../ThemeSwitcher';
import HireMeModal from '../HireMeModal.vue';
import feather from 'feather-icons';
import AppHeaderLinks from './AppHeaderLinks.vue';
import Button from '../reusable/Button.vue';

export default {
	components: {
		ThemeSwitcher,
		HireMeModal,
		AppHeaderLinks,
		Button,
	},
	data() {
		return {
			isOpen: false,
			theme: '',
			modal: false,
			categories: [
				{
					id: 1,
					value: 'backend',
					name: 'Back End Developer',
				},
				{
					id: 2,
					value: 'frontend',
					name: 'Front End Developer',
				},
				{
					id: 3,
					value: 'fullstack',
					name: 'Full Stack Developer',
				},
			],
		};
	},

	created() {
		this.theme = localStorage.getItem('theme') || 'light';
	},
	mounted() {
		feather.replace();
		this.theme = localStorage.getItem('theme') || 'light';
	},
	methods: {
		updateTheme(theme) {
			this.theme = theme;
		},
		showModal() {
			if (this.modal) {
				// Stop screen scrolling
				document
					.getElementsByTagName('html')[0]
					.classList.remove('overflow-y-hidden');
				this.modal = false;
			} else {
				document
					.getElementsByTagName('html')[0]
					.classList.add('overflow-y-hidden');
				this.modal = true;
			}
		},
	},
	updated() {
		feather.replace();
	},
};
</script>

<template>
	<nav id="nav" class="sm:container sm:mx-auto">
		<!-- Header start -->
		<div
			class="z-10 max-w-screen-lg xl:max-w-screen-xl block sm:flex sm:justify-between sm:items-center my-6"
		>

			<!-- Header links -->
			<AppHeaderLinks :showModal="showModal" :isOpen="isOpen" />

			<!-- Header right section buttons -->
			<div
				class="hidden sm:flex justify-between items-center flex-col md:flex-row"
			>
				<!-- Hire me button -->
				<div class="hidden md:block">
					<Button
						title="Hire Me"
						class="text-md font-general-medium bg-indigo-500 hover:bg-indigo-600 text-white shadow-sm rounded-md px-5 py-2.5 duration-300"
						@click="showModal()"
						aria-label="Hire Me Button"
					/>
				</div>

				<!-- Theme switcher large screen -->
				<theme-switcher
					:theme="theme"
					@themeChanged="updateTheme"
					class="ml-5 bg-primary-light dark:bg-ternary-dark px-3 py-2 shadow-sm rounded-lg cursor-pointer"
				/>
			</div>
		</div>

		<!-- Hire me modal -->
		<HireMeModal
			:showModal="showModal"
			:modal="modal"
			:categories="categories"
			aria-modal="Hire Me Modal"
		/>
	</nav>
</template>

<style scoped>
#nav a.router-link-exact-active {
	@apply text-indigo-700;
	@apply dark:text-indigo-400;
	@apply font-medium;
}
</style>
