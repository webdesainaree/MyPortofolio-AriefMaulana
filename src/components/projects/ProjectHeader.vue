<script>
import dataProjects from '../../data/projects';

export default {
	props: ['singleProjectHeader','id'],
	data: () => {
		return {
			dataProjects,
		}
	},
	created() {
		this.loadProject(this.id);
	},
	methods: {
		loadProject(id) {
		// Retrieve project data based on the provided ID
		this.project = this.dataProjects.find((project) => project.id === parseInt(id));
		},
	},
};
</script>

<template>
	<div>
		<!-- Project heading and meta info -->
		<p
			class="font-general-medium text-left text-3xl sm:text-4xl font-bold text-primary-dark dark:text-primary-light mt-14 sm:mt-20 mb-7"
		>
			{{ singleProjectHeader.singleProjectTitle }} 
		</p>
		{{ project }}
		<div v-if="project">
			<h2>{{ project.title }}</h2>
			<p>{{ project.description }}</p>
		</div>
		<div v-else>
			<p>Project not found</p>
		</div>
		<div class="flex">
			<div class="flex items-center mr-10">
				<i
					data-feather="clock"
					class="w-4 h-4 text-ternary-dark dark:text-ternary-light"
				></i>
				<span
					class="font-general-medium ml-2 leading-none text-primary-dark dark:text-primary-light"
					>{{ singleProjectHeader.singleProjectDate }}</span
				>
			</div>
			<div class="flex items-center">
				<i
					data-feather="tag"
					class="w-4 h-4 text-ternary-dark dark:text-ternary-light"
				></i>
				<span
					class="font-general-medium ml-2 leading-none text-primary-dark dark:text-primary-light"
					>{{ singleProjectHeader.singleProjectTag }}</span
				>
			</div>
		</div>
	</div>
</template>
