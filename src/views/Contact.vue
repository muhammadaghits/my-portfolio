<script>
import feather from 'feather-icons';
import ContactForm from '@/components/contact/ContactForm.vue';
import ContactDetails from '@/components/contact/ContactDetails.vue';

export default {
	components: {
		ContactForm,
		ContactDetails,
	},
	data: () => {
		return {
			contacts: [
				{
					id: 1,
					name: 'Bandung, Indonesia',
					icon: 'map-pin',
					url: 'https://maps.app.goo.gl/iC2xg2wmGTdSYLxNA',
				},
				{
					id: 2,
					name: 'muhammadaghits@gmail.com',
					icon: 'mail',
					url: 'mailto:muhammadaghits@gmail.com',
				},
				{
					id: 3,
					name: '+6281210166462',
					icon: 'phone',
					url: 'https://wa.link/qgm39q',
				},
			],
		};
	},
	mounted() {
		feather.replace();
	},
	updated() {
		feather.replace();
	},
	methods: {},
};
</script>

<template>
	<div
		class="container mx-auto flex flex-col-reverse md:flex-row py-5 md:py-10 md:mt-10"
	>
		<!-- Contact form -->
		<ContactForm />

		<!-- Contact details -->
		<ContactDetails :contacts="contacts" />
	</div>
</template>
