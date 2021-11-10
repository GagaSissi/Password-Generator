<template>
  <section>
    <h1>{{ message }}</h1>
    <p>Kumulierte Password Werte</p>
    <button @click="copyYourPassword">Copy Your Password</button>
    <p>unsichtbar</p>
  </section>
  <section>
    <form v-on:submit.prevent="add">
      <input type="checkbox" class="buttonCheckbox" id="labelID1" />
      <label class="labelButton" for="labelID1">Lowercase</label>
    </form>
    <form v-on:submit.prevent="add">
      <p>Password Lenght:</p>
      <input type="range" class="slidingTool" id="labelID2" />
      <label class="labelSlider" for="labelID2" min="1" max="15"
        >irgendein wert</label
      >
    </form>
  </section>
</template>

<script>
export default {
  name: "PasswordGenerator",
  props: {
    message: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*,
*::before,
*::after {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
.buttonCheckbox {
  all: unset;
}

.labelButton {
  padding: 0 0.2rem;
  border: 0.2rem solid pink;
  border-radius: 0.2rem;
}

.buttonCheckbox:checked + .labelButton {
  background-color: black;
  color: white;
}

.buttonCheckbox:focus + .labelButton {
  border: 0.2rem solid pink;
}

p {
  margin-top: 7rem;
}

.slidingTool {
  -webkit-appearance: none;
  appearance: none;
  background-color: white;
  height: 0.5rem;
  border-radius: 0.5rem;
}

.slidingTool::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 1rem;
  height: 1rem;
  background: pink;
  border-radius: 50%;
}
</style>
