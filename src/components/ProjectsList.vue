<template>
  <div class="projects-list">
    <ProjectCard
      v-for="project in projects"
      :project="project"
      :key="project.id"
    />
  </div>
</template>

<script>
import ProjectCard from "./ProjectCard.vue";
import projects from "../data/projects";

export default {
  name: "ProjectsList",
  components: {
    ProjectCard,
  },
  data() {
    return {
      projects,
    };
  },
};
</script>

<style scoped>
.projects-list {
  display: grid;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 16px;
  grid-template-columns: 1fr 1fr;
  column-gap: 24px;
  row-gap: 34px;
}
</style>
