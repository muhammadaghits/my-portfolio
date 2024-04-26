<script>
import Button from '../reusable/Button.vue';
import FormInput from '../reusable/FormInput.vue';
import FormTextarea from '../reusable/FormTextarea.vue';
import emailjs from '@emailjs/browser';
// import Swal from 'sweetalert2';
export default {
	components: { Button, FormInput, FormTextarea },
	methods: {
		sendEmail() {
			emailjs.sendForm('service_58qlcra', 'template_z5wwsad', this.$refs.form, {
				publicKey: '_cUQWt4uiCi9m31EG',
			})
			.then((result) => {
				console.log('SUCCESS!', result.text);
				this.$refs.form.reset();
			},
			(error) => {
				console.log('FAILED...', error.text);
			},);
		},
		// handleAlertClick() {
		// 	Swal.fire('Success');
		// },
	},
};
</script>

<template>
	<div class="w-full md:w-4/4 ml-7">
		<div
			class="leading-loose max-w-3xl m-4 p-7 bg-secondary-light dark:bg-secondary-dark rounded-xl shadow-xl text-left"
		>
			<p
				class="font-general-medium text-primary-dark dark:text-primary-light text-2xl mb-8"
			>
				Contact Form
			</p>
			<form ref="form" @submit.prevent="sendEmail" class="font-general-regular space-y-4">
        <div class="flex flex-wrap">
          <div class="w-full md:w-1/2 pr-2">
				<FormInput label="Full Name" inputIdentifier="name" />
          </div>
          <div class="w-full md:w-1/2 pl-1">
				<FormInput
					label="Email"
					inputIdentifier="email"
					inputType="email"
				/>
          </div>
        </div>
				<FormInput label="Subject" inputIdentifier="subject" />
				<FormTextarea label="Message" textareaIdentifier="message" />

				<div>
					<Button
						title="Send Message"
						class="px-4 py-2.5 text-white tracking-wider bg-indigo-500 hover:bg-indigo-600 focus:ring-1 focus:ring-indigo-900 rounded-lg duration-500"
						type="submit"
						aria-label="Send Message"
					/>
				</div>
			</form>
		</div>
	</div>
</template>

<style lang="scss" scoped></style>
