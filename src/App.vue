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
@import url("https://fonts.googleapis.com/css2?family=Arvo:wght@700&display=swap");
#app {
  font-family: "Arvo", serif;
  text-align: center;
  --light-color: #f5efed;
  color: var(--light-color);
  margin-top: 60px;
}

html {
  height: 100%;
}

:root {
  --dark-color: #0f0a0a;
  background-color: var(--dark-color);
}

button {
  font-family: inherit;
}
</style>
