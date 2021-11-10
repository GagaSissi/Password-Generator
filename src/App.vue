<template>
  <PasswordGenerator message="Password Generator" />
</template>

<script>
import PasswordGenerator from "./components/PasswordGenerator.vue";

export default {
  name: "App",
  components: {
    PasswordGenerator,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  --light-color: #f5efed;
  color: var(--light-color);
  margin-top: 60px;
}

:root {
  --dark-color: #0f0a0a;
  background-color: var(--dark-color);
}
</style>
