<template>
  <header>
    <h1>project hub</h1>
    <p>Hello, my name is Kamila Lach. This is my project hub.</p>
  </header>
</template>

<script>
export default {
  name: "TheHeader",
};
</script>

<style scoped>
header {
  max-width: 1200px;
  margin: 0 auto;
  padding: 60px 20px;
}
h1 {
  font-weight: 600;
  padding-bottom: 12px;
}

@media (max-width: 700px) {
  header {
    padding: 45px 20px;
  }
} ;
</style>
