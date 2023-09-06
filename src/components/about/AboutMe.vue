<script>
export default {
	setup() {
		return {
			bios: [
				{
					id: 1,
					bio:
						'Saya adalah seorang desainer UI/UX dan web dengan pengalaman yang kuat dalam menciptakan pengalaman pengguna yang menarik dan berfokus pada desain yang estetis dan fungsional. Dengan latar belakang dalam menggabungkan desain web yang inovatif dengan pemahaman mendalam tentang kebutuhan pengguna, saya bertujuan untuk menghasilkan solusi desain yang memikat dan memenuhi tujuan bisnis.',
				},
				{
					id: 2,
					bio:
						'Saya memahami bahwa desain bukan hanya tentang estetika, tetapi juga tentang menciptakan solusi yang memecahkan masalah dan memenuhi kebutuhan pengguna. Saya selalu berusaha untuk menggabungkan kreativitas dengan fungsionalitas dalam setiap proyek yang saya tangani. Saya percaya bahwa pengalaman pengguna yang luar biasa adalah kunci keberhasilan produk dan bisnis, dan saya berkomitmen untuk mencapai hal itu.',
				},
			],
		};
	},
};
</script>

<template>
	<div class="block sm:flex sm:gap-10 mt-10 sm:mt-20">
		<!-- About profile image -->
		<div class="w-full sm:w-1/4 mb-7 sm:mb-0">
			<img
				src="@/assets/images/profile.jpeg"
				class="rounded-xl w-96"
				alt=""
			/>
		</div>

		<!-- About details -->
		<div class="w-full sm:w-3/4 text-left">
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
