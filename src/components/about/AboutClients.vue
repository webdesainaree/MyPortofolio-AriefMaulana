<script>
import AboutClientSingle from './AboutClientSingle.vue';

export default {
	components: {
		AboutClientSingle,
	},
	data: () => {
		return {
			clientsHeading: 'Some of the brands I have worked with',
			clients: [
				{
					id: 1,
					title: 'SBM ITB',
					img: 'https://ik.imagekit.io/dc6b0ongfr/client/sbm_8cjSF31OhE.png?updatedAt=1673412944709',
				},
				{
					id: 2,
					title: 'UNHI',
					img: ('https://ik.imagekit.io/dc6b0ongfr/client/unhi_k9hf5lEOY.png?updatedAt=1673412944749'),
				},
				{
					id: 3,
					title: 'bpbrin',
					img: ('https://ik.imagekit.io/dc6b0ongfr/client/bpbrin_CLCrFOjJo.png?updatedAt=1673412944580'),
				},
				{
					id: 4,
					title: 'univ bakrie',
					img: ('https://ik.imagekit.io/dc6b0ongfr/client/Logo-Universitas-Bakrie-Original-Lengkap-png_EeoPq-x2N9.png?updatedAt=1674790679680'),
				},
				{
					id: 5,
					title: 'mikti',
					img: ('https://ik.imagekit.io/dc6b0ongfr/client/logomikti-sm_0yV2p6uM8.png?updatedAt=1684740669524'),
				},
				{
					id: 6,
					title: 'power commerce',
					img: ('https://ik.imagekit.io/dc6b0ongfr/client/pca_N67tmLibR.png?updatedAt=1673412944632'),
				},
				{
					id: 7,
					title: 'bekup',
					img: ('https://ik.imagekit.io/dc6b0ongfr/client/logobekup_beMzdH87u.png?updatedAt=1684747587645'),
				},
				{
					id: 7,
					title: 'amoeba',
					img: ('https://ik.imagekit.io/dc6b0ongfr/client/Logo_Amoeba-sm_3drr5LANi.png?updatedAt=1684740515893'),
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
			Beberapa Perusahaan dan Universitas<br> yang pernah bekerja sama dengan saya
		</p>
		<div class="grid grid-cols-2 sm:grid-cols-4 mt-10 sm:mt-14 gap-2">
			<AboutClientSingle
				v-for="client in clients"
				:key="client.id"
				:client="client"
			/>
		</div>
	</div>
</template>
