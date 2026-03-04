<template>
  <section id="projects" class="bg-dark py-5">
    <div class="container">

      <div class="row mb-4 text-center">
        <div class="col-12">
          <h2 class="text-light text-project">My Projects</h2>
        </div>
      </div>

      <!-- Loop per chunk (row) -->
      <div
        v-for="(group, index) in chunkedProjects"
        :key="index"
        class="row g-4 mb-4 justify-content-center"
      >
        <!-- Loop per project (column) -->
        <div
          v-for="project in group"
          :key="project.id"
          class="col-12 col-sm-6 col-md-4 d-flex"
        >
          <ProjectCard :project="project" />
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
	

	import {computed} from "vue";
	import ProjectCard from "./ProjectCard.vue";
	import projects from "../data/project.json";

		const chunkSize = 3;

		const chunkedProjects = computed(() => {

			const chunks = [];

			for(let i = 0; i < projects.length; i+=chunkSize){
				chunks.push(projects.slice(i, i+chunkSize));
			}

			return chunks;
		})
</script>