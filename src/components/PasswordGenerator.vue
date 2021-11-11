<template>
  <main>
    <section>
      <h1>{{ message }}</h1>
      <p class="passwordID">Kumulierte Password Werte</p>
      <button @click="copyYourPassword">Copy Your Password</button>
      <p>unsichtbar</p>
    </section>
    <section>
      <input
        type="checkbox"
        class="buttonLowercase"
        id="labelID1"
        v-model="lowerCaseCharakters"
      />
      <label class="labelButton" for="labelID1">Lowercase</label>
      <input
        type="checkbox"
        class="buttonUppercase"
        id="labelID2"
        v-model="upperCaseCharakters"
      />
      <label class="labelButton" for="labelID2">Uppercase</label>
    </section>
    <section>
      <input
        type="checkbox"
        class="buttonNumbers"
        id="labelID3"
        v-model="numbersCharakters"
      />
      <label class="labelButton" for="labelID3">Numbers</label>
      <input
        type="checkbox"
        class="buttonSymbols"
        id="labelID4"
        v-model="objectsCharakters"
      />
      <label class="labelButton" for="labelID4">Symbols</label>
    </section>
    <section>
      <p>Password Lenght:</p>
      <input
        type="range"
        class="slidingTool"
        id="labelrangeID1"
        min="8"
        max="35"
        v-model="value"
        @input="getYourPassword"
      />
      <label class="labelSlider" for="labelrangeID1">{{ value }}</label>
    </section>
  </main>
</template>

<script>
export default {
  name: "PasswordGenerator",
  data() {
    return {
      value: 8,
      newgetYourPassword: "",
      lowerCaseCharakters: true,
      upperCaseCharakters: false,
      numbersCharakters: false,
      objectsCharakters: false,
    };
  },
  methods: {
    getYourPassword() {
      let result = "";
      let characters = "";
      if (this.lowerCaseCharakters) {
        characters += "abcdefghijklmnopqrstuvwxyz";
      }
      for (let i = 0; i < this.value; i++) {
        result += characters.charAt(
          Math.floor(Math.random() * characters.length)
        );
      }
      this.newgetYourPassword = result;
      console.log(result);
    },
  },
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

main {
  font-size: 1.25em;
  display: grid;
  justify-content: center;
}

section {
}

p {
  margin: 3em;
}

button {
  font-size: 1rem;
  background-color: var(--accent-color);
  padding: 0.5rem 0.5rem;
  border: 0.1rem solid var(--dark-color);
  border-radius: 0.2rem;
  width: 200px;
}

input {
  all: unset;
}

.labelSlider {
  margin: 1em;
}

#labelID1,
#labelID2,
#labelID3,
#labelID4 {
  margin: 3em;
}

/* Sliding Bar*/
/* Hier länge der Bar einstellen */
input[type="range"] {
  width: 30em;
}

.labelButton {
  padding: 0 1.5rem;
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
