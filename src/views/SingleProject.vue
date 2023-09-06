<script>
import feather from 'feather-icons';
// import ProjectHeader from '../components/projects/ProjectHeader.vue';
// import ProjectGallery from '../components/projects/ProjectGallery.vue';
// import ProjectInfo from '../components/projects/ProjectInfo.vue';
import ProjectRelatedProjects from '../components/projects/ProjectRelatedProjects.vue';
import dataProjects from '../data/projects';

export default {
	name: 'Projects',
	props: ['id'],
	components: {
		// ProjectHeader,
		// ProjectGallery,
		// ProjectInfo,
		ProjectRelatedProjects,
	},
	data: () => {
		return {
			dataProjects,
			singleProjectHeader: 
				{
					id: 1,
					singleProjectTitle: 'Project Management UI',
					singleProjectDate: 'September, 2023',
					singleProjectTag: 'UI / Frontend',
				},
			
			projectInfo: {
				clientHeading: 'About Client',
				companyInfos: [
					{
						id: 1,
						title: 'Name',
						details: 'Company Ltd',
					},
					{
						id: 2,
						title: 'Services',
						details: 'UI Design & Frontend Development',
					},
					{
						id: 3,
						title: 'Website',
						details: 'https://company.com',
					},
					{
						id: 4,
						title: 'Phone',
						details: '555 8888 888',
					},
				],
				technologies: [
					{
						title: 'Tools & Technologies',
						techs: [
							'HTML',
							'CSS',
							'JavaScript',
							'Vue.js',
							'Vuetify',
							'Figma',
						],
					},
				],
				socialSharings: [
					// {
					// 	id: 1,
					// 	name: 'Twitter',
					// 	icon: 'twitter',
					// 	url: 'https://twitter.com/',
					// },
					{
						id: 2,
						name: 'Instagram',
						icon: 'instagram',
						url: 'https://instagram.com/aipteaeuy',
					},
					{
						id: 3,
						name: 'Facebook',
						icon: 'facebook',
						url: 'https://facebook.com/aip.ajah',
					},
					{
						id: 4,
						name: 'LinkedIn',
						icon: 'linkedin',
						url: 'www.linkedin.com/in/arief-maulana-ssi',
					},
					// {
					// 	id: 5,
					// 	name: 'Youtube',
					// 	icon: 'youtube',
					// 	url: 'https://www.youtube.com',
					// },
				],
			},
			relatedProject: {
				relatedProjectsHeading: 'Related Projects',
				relatedProjects: [
					{
						id: 1,
						title: 'Mobile UI',
						img: require('@/assets/images/vinovj.png'),
					},
					{
						id: 2,
						title: 'Web Application',
						img: require('@/assets/images/konsulta.png'),
					},
					{
						id: 3,
						title: 'UI Design',
						img: require('@/assets/images/vinovco.jpg'),
					},
					{
						id: 4,
						title: 'Kabul Mobile App UI',
						img: require('@/assets/images/startupm.png'),
					},
				],
			},
		};
	},
	mounted() {
		feather.replace();
	},
	updated() {
		feather.replace();
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
	<div class="container mx-auto mt-10 sm:mt-20">
		<!-- {{ project }} -->

		<div v-if="project">
			<p class="font-general-medium text-left text-3xl sm:text-4xl font-bold text-primary-dark dark:text-primary-light mt-14 sm:mt-20 mb-7">
				{{ project.title }}
			</p>
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

		<!-- {{ project.title }} -->
		<!-- Project header -->
		<!-- <ProjectHeader :singleProjectHeader="singleProjectHeader" /> -->

		<!-- Project gallery -->
		<!-- <ProjectGallery :projectImages="projectImages" /> -->
		
		<div class="grid grid-cols-1 sm:grid-cols-3 sm:gap-10 mt-12">
			<div class="mb-10 sm:mb-0">
				<img
					:src="project.img"
					class="rounded-xl cursor-pointer shadow-lg sm:shadow-none"
				/>
			</div>
			<div class="mb-10 sm:mb-0">
				<img
					style="max-height: 300px; margin: 0 auto;"
					:src="project.img2"
					class="rounded-xl cursor-pointer shadow-lg sm:shadow-none"
				/>
			</div>
			<div class="mb-10 sm:mb-0">
				<img
					style="max-height: 300px; margin: 0 auto;"
					:src="project.img3"
					class="rounded-xl cursor-pointer shadow-lg sm:shadow-none"
				/>
			</div>
		</div>

		<!-- Project information -->
		<!-- <ProjectInfo :projectInfo="projectInfo" /> -->

		<div class="block sm:flex gap-0 sm:gap-10 mt-14">
		<!-- Single project left section details -->
		<div class="w-full sm:w-1/3 text-left">
			<!-- Single project client details -->
			<div class="mb-7">
				<p
					class="font-general-medium text-2xl text-secondary-dark dark:text-secondary-light mb-2"
				>
					{{ projectInfo.clientHeading }}
				</p>
				<ul class="leading-loose">
					<li class="font-general-regular text-ternary-dark dark:text-ternary-light">
						App Name: <b style="color: grey;">{{ project.name }}</b>
					</li>
					<li class="font-general-regular text-ternary-dark dark:text-ternary-light">
						Services: <b style="color: grey;">{{ project.services }}</b>
					</li>
					<li class="font-general-regular text-ternary-dark dark:text-ternary-light">
						Company: <b style="color: grey;">{{ project.company }}</b>
					</li>
					<li class="font-general-regular text-ternary-dark dark:text-ternary-light">
						Website: <b style="color: grey;">{{ project.web }}</b>
					</li>
					
					
				</ul>
			</div>

			<!-- Single project objectives -->
			<div class="mb-7">
				<p
					class="font-general-medium text-2xl text-ternary-dark dark:text-ternary-light mb-2"
				>
					Objective
				</p>
				<p
					class="font-general-regular text-primary-dark dark:text-ternary-light"
				>
					{{ project.obj }}
				</p>
			</div>

			<!-- Single project technologies -->
			<div class="mb-7">
				<p
					class="font-general-medium text-2xl text-ternary-dark dark:text-ternary-light mb-2"
				>
					{{ projectInfo.technologies[0].title }}
				</p>
				<p
					class="font-general-regular text-primary-dark dark:text-ternary-light"
				>
					{{ projectInfo.technologies[0].techs.join(', ') }}
				</p>
			</div>

			<!-- Single project social sharing -->
			<div>
				<p
					class="font-general-medium text-2xl text-ternary-dark dark:text-ternary-light mb-2"
				>
					Medial Social
				</p>
				<div class="flex items-center gap-3 mt-5">
					<a
						v-for="social in projectInfo.socialSharings"
						:key="social.id"
						:href="social.url"
						target="__blank"
						aria-label="Share Project"
						class="bg-ternary-light dark:bg-ternary-dark text-gray-400 hover:text-primary-dark dark:hover:text-primary-light p-2 rounded-lg shadow-sm duration-500"
						><i
							:data-feather="social.icon"
							class="w-4 lg:w-5 h-4 lg:h-5"
						></i
					></a>
				</div>
			</div>
		</div>

		<!-- Single project right section details -->
		<div class="w-full sm:w-2/3 text-left mt-10 sm:mt-0">
			<p
				class="font-general-medium text-primary-dark dark:text-primary-light text-2xl font-bold mb-7"
			>
				Description
			</p>
			<p class="font-general-regular mb-5 text-lg text-ternary-dark dark:text-ternary-light">
				{{ project.description }}
			</p>
		</div>
	</div>

		<!-- Project related projects -->
		<ProjectRelatedProjects :relatedProject="relatedProject" />
	</div>
</template>

<style scoped></style>
