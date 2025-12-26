<template>
  <section id="projects">
    <h2>Mes projets</h2>

    <div class="projects-grid">
      <ProjectCard
        v-for="project in FilteredProjects"
        :key="project.id"
        :project="project"
      />
    </div>
  </section>
</template>

<script setup>
import { projects } from '@/data/projects'
import ProjectCard from './ProjectCard.vue'

const FilteredProjects = projects;

</script>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 2rem;
  width: 100%;
}

#projects{
  padding-bottom: 4rem;
  width: 100%;
}
</style>
