<template>
  <TheHeader />
  <ProjectsList class="project-list" />
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import ProjectsList from "./components/ProjectsList.vue";

export default {
  components: {
    TheHeader,
    ProjectsList,
  },
};
</script>

<style>
*,
*::before,
*::after {
  font-family: "Raleway";
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
