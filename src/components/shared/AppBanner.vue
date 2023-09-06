<script>
import feather from 'feather-icons';

export default {
	name: 'Home',
	data: () => {
		return {
			theme: '',
		};
	},
	created() {
		this.theme = localStorage.getItem('theme') || 'light';
	},
	mounted() {
		feather.replace();
		this.theme = localStorage.getItem('theme') || 'light';
	},
	updated() {
		feather.replace();
	},
	methods: {},
};
</script>

<template>
	<section
		class="flex flex-col sm:justify-between items-center sm:flex-row mt-10 sm:mt-10"
	>
		<!-- Banner left contents -->
		<div class="md:w-auto text-left xl:text-right xl:w-max">
			<h1
				class="font-general-semibold text-3xl md:text-3xl xl:text-4xl text-center sm:text-left text-ternary-dark dark:text-primary-light uppercase"
			>
				Halo, <br>Nama Saya<br> Arief Maulana
			</h1>
			<p
				class="font-general-medium mt-2 text-lg sm:text-xl  xl:text-2xl text-center sm:text-left leading-none text-gray-400"
			>
				Seorang UI/UX Designer & Web Designer
			</p>
			<div class="flex row">
				<div class="col-span-6 mr-3">
					<a
						download="cv_ariefmaulana_ats.pdf"
						href="/files/cv_ariefmaulana_ats.pdf"
						class="flex justify-center items-center w-36 sm:w-48 mt-12 mb-6 sm:mb-0 text-lg border border-indigo-200 dark:border-ternary-dark py-2.5 sm:py-3 shadow-lg rounded-lg bg-indigo-50 focus:ring-1 focus:ring-indigo-900 hover:bg-blue-500 text-gray-500 hover:text-white duration-500"
						aria-label="Download Resume"
					>
						<i
							data-feather="arrow-down-circle"
							class="ml-0 sm:ml-1 mr-2 sm:mr-3 w-5 sm:w-6 duration-100"
						></i>
						<span
							class="text-sm sm:text-lg font-general-medium duration-100"
							>Unduh CV</span
						></a
					>
				</div>
				<div class="col-span-6">
					<a
						download="Surat_Refrensi_Kerja_paklaring_Arief_Maulana_PTbarapraja.pdf"
						href="/files/Surat_Refrensi_Kerja_paklaring_Arief_Maulana_PTbarapraja.pdf"
						class="flex justify-center items-center w-36 sm:w-48 mt-12 mb-6 sm:mb-0 text-lg border border-indigo-200 dark:border-ternary-dark py-2.5 sm:py-3 shadow-lg rounded-lg bg-indigo-50 focus:ring-1 focus:ring-indigo-900 hover:bg-blue-500 text-gray-500 hover:text-white duration-500"
						aria-label="Download Resume"
					>
						<i
							data-feather="arrow-down-circle"
							class="ml-0 sm:ml-1 mr-2 sm:mr-3 w-5 sm:w-6 duration-100"
						></i>
						<span
							class="text-sm sm:text-lg font-general-medium duration-100"
							>Paklaring</span
						></a
					>
				</div>			
			</div>
		</div>

		<!-- Banner right illustration -->
		<div class="w-full md:w-1/2 text-right float-right xl:mr-5">
			<img
				v-if="theme === 'light'"
				src="@/assets/images/arief.png"
				width=""
				alt="Developer"
			/>
			<img
				v-else
				src="@/assets/images/arief.png"
				alt="Developer"
			/>
		</div>
	</section>
</template>

<style scoped></style>
