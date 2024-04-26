<script>
export default {
	setup() {
		return {
			bios: [
				{
					id: 1,
					bio:
            "My name is Muhammad Aghits Septian Alfarizi. I'm 25 years old. I graduated with a bachelor's degree in Informatics Engineering from Indonesia Computer University (UNIKOM) with GPA of 3.32.",
        },
				{
					id: 2,
					bio:
              "I'm a web developer with one year of experience in designing, developing, and maintaining responsive websites. I'm skilled in using web technologies such as HTML5, CSS3, JavaScript, and PHP. I usually use modern frameworks such as Bootstrap, Tailwind CSS, React.js, or Vue.js for front-end development, as well as Codeigniter or Laravel for back-end development. Meanwhile, for database management systems, I usually use Oracle or MySQL.",
				},
				{
					id: 3,
					bio:
              "I have strong problem-solving skills and a passion for staying up to date with the latest web technologies, and I'm committed to delivering high-quality projects on time.",
				},
			],
		};
	},
};
</script>

<template>
	<div class="block sm:flex sm:gap-9 mt-10 sm:mt-20">
		<!-- About profile image -->
		<div class="w-full sm:w-1/4 mb-7 sm:mb-0">
			<img
				src="../../assets/images/profile.jpeg"
				class="rounded-3xl w-64"
				alt="Profile"
			/>
		</div>

		<!-- About details -->
		<div class="w-full sm:w-3/4 text-justify">
			<p
				v-for="bio in bios"
				:key="bio.id"
				class="font-general-regular mb-4 text-ternary-dark dark:text-ternary-light text-lg"
			>
				{{ bio.bio }}
			</p>
		</div>
	</div>
</template>
