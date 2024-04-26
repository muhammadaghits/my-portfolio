<script>
import AboutClientSingle from './AboutClientSingle.vue';

export default {
	components: {
		AboutClientSingle,
	},
	data: () => {
		return {
			clientsHeading: 'My Skills',
			clients: [
				{
					id: 1,
					title: 'HTML',
					img: require('@/assets/images/skills/html.svg'),
					alt: 'HTML',
				},
				{
					id: 2,
					title: 'CSS',
					img: require('@/assets/images/skills/css.svg'),
					alt: 'CSS',
				},
				{
					id: 3,
					title: 'Bootstrap',
					img: require('@/assets/images/skills/bootstrap.svg'),
					alt: 'Bootstrap',
				},
				{
					id: 4,
					title: 'Tailwind CSS',
					img: require('@/assets/images/skills/tailwind-css.svg'),
					alt: 'Tailwind CSS',
				},
				{
					id: 5,
					title: 'JavaScript',
					img: require('@/assets/images/skills/javascript.svg'),
					alt: 'JavaScript',
				},
				{
					id: 6,
					title: 'VueJS',
					img: require('@/assets/images/skills/vue-js.svg'),
					alt: 'VueJS',
				},
				{
					id: 7,
					title: 'ReactJS',
					img: require('@/assets/images/skills/react-js.svg'),
					alt: 'ReactJS',
				},
				{
					id: 8,
					title: 'PHP',
					img: require('@/assets/images/skills/php.svg'),
					alt: 'PHP',
				},
				{
					id: 9,
					title: 'CodeIgniter',
					img: require('@/assets/images/skills/codeigniter.svg'),
					alt: 'CodeIgniter',
				},
				{
					id: 10,
					title: 'Laravel',
					img: require('@/assets/images/skills/laravel.svg'),
					alt: 'Laravel',
				},
				{
					id: 11,
					title: 'MySQL',
					img: require('@/assets/images/skills/mysql.svg'),
					alt: 'MySQL',
				},
				{
					id: 12,
					title: 'Oracle',
					img: require('@/assets/images/skills/oracle.svg'),
					alt: 'Oracle',
				},
				{
					id: 13,
					title: 'Git',
					img: require('@/assets/images/skills/git.svg'),
					alt: 'Git',
				},
				{
					id: 14,
					title: 'RESTful API',
					img: require('@/assets/images/skills/api.svg'),
					alt: 'RESTful API',
				},
			],
		};
	},
};
</script>

<template>
	<div class="mt-10 sm:mt-20">
		<p
			class="font-general-medium text-2xl sm:text-3xl text-primary-dark dark:text-primary-light"
		>
			{{ clientsHeading }}
		</p>
		<div class="grid grid-cols-3 sm:grid-cols-7 mt-10 sm:mt-14 gap-2">
			<AboutClientSingle
				v-for="client in clients"
				:key="client.id"
				:client="client"
			/>
		</div>
	</div>
</template>