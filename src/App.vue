<template>
  <div class="main">
    <TheHeader />
    <ProjectsList class="project-list" />
  </div>
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

.main {
  background: #f5f5f5;
}
</style>
