<template>
  <section>
    <h1>{{ message }}</h1>
    <p>Kumulierte Password Werte</p>
    <button @click="copyYourPassword">Copy Your Password</button>
    <p>unsichtbar</p>
  </section>
  <section>
    <form v-on:submit.prevent="add">
      <input type="checkbox" class="buttonLowercase" id="labelID1" />
      <label class="labelButton" for="labelID1">Lowercase</label>
      <input type="checkbox" class="buttonUppercase" id="labelID2" />
      <label class="labelButton" for="labelID2">Uppercase</label>
      <input type="checkbox" class="buttonNumbers" id="labelID3" />
      <label class="labelButton" for="labelID3">Numbers</label>
      <input type="checkbox" class="buttonSymbols" id="labelID4" />
      <label class="labelButton" for="labelID4">Symbols</label>
    </form>
    <form v-on:submit.prevent="add">
      <p>Password Lenght:</p>
      <input
        type="range"
        class="slidingTool"
        id="labelrangeID1"
        min="8"
        max="35"
      />
      <label class="labelSlider" for="labelrangeID1">irgendein wert</label>
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
  --dark-color: #0f0a0a;
  --light-color: #f5efed;
  --accent-color: #2292a4;
  --success-color: #cbe896;
}

section {
  font-size: 1.25em;
}

p {
  margin: 3em;
}

input {
  all: unset;
  /* margin: 1em; */
  padding: 0.1em 0.4em;
}

.labelButton {
  padding: 0 1rem;
  border: 0.2rem solid var(--accent-color);
  border-radius: 0.2rem;
}

.buttonLowercase:checked + .labelButton {
  background-color: var(--accent-color);
  color: var(--light-color);
}

.buttonUppercase:checked + .labelButton {
  background-color: var(--accent-color);
  color: var(--light-color);
}

.buttonNumbers:checked + .labelButton {
  background-color: var(--accent-color);
  color: var(--light-color);
}

.buttonSymbols:checked + .labelButton {
  background-color: var(--accent-color);
  color: var(--light-color);
}

.buttonLowercase:focus + .labelButton {
  border: 0.2rem solid var(--accent-color);
}

/* Sliding Bar*/
/* Länge einstellen, wie? */

.slidingTool {
  -webkit-appearance: none;
  appearance: none;
  background-color: var(--light-color);
  height: 0.5rem;
  border-radius: 0.5rem;
}

.slidingTool::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 1.5rem;
  height: 1.5rem;
  background: var(--accent-color);
  border-radius: 50%;
}
</style>
