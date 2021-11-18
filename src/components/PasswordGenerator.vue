<template>
  <main>
    <section>
      <h1>{{ message }}</h1>
      <p class="passwordID">Hallo {{ result }}</p>
      <button @click="copyYourPassword">Copy Your Password</button>
      <p>unsichtbar</p>
    </section>
    <article class="grid-container">
      <section class="grid-box1">
        <input
          type="checkbox"
          class="buttonLowercase"
          id="labelID1"
          v-model="lowerCaseCharakters"
        />
        <label class="labelButton" for="labelID1">Lowercase</label>
      </section>
      <section class="grid-box2">
        <input
          type="checkbox"
          class="buttonUppercase"
          id="labelID2"
          v-model="upperCaseCharakters"
        />
        <label class="labelButton" for="labelID2">Uppercase</label>
      </section>
      <section class="grid-box3">
        <input
          type="checkbox"
          class="buttonNumbers"
          id="labelID3"
          v-model="numbersCharakters"
        />
        <label class="labelButton" for="labelID3">Numbers</label>
      </section>
      <section class="grid-box4">
        <input
          type="checkbox"
          class="buttonSymbols"
          id="labelID4"
          v-model="objectsCharakters"
        />
        <label class="labelButton" for="labelID4">Symbols</label>
      </section>
    </article>
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
      result: "",
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
      return result;
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
  width: 50rem;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

.grid-container {
  font-size: 1.25rem;
  height: 7rem;
  display: grid;
  grid-template-columns: 25% 1fr 1fr 25%;
  grid-template-rows: 50% 50%;
}

.grid-box1 {
  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 1;
  grid-row-end: 2;
}

.grid-box2 {
  grid-column-start: 2;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 2;
}

.grid-box3 {
  grid-column-start: 3;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 2;
}

.grid-box4 {
  grid-column-start: 4;
  grid-column-end: 5;
  grid-row-start: 1;
  grid-row-end: 2;
}

p {
  margin: 1rem;
  height: 3rem;
}

.passwordID {
  width: 100%;
  color: var(--light-color);
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

/* Sliding Bar*/
/* Hier länge der Bar einstellen */
input[type="range"] {
  width: 30rem;
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

@media screen and (max-width: 800px) {
  .grid-container {
    font-size: 1.25rem;
    display: grid;
    grid-template-columns: 50% 50%;
    grid-template-rows: 50% 50%;
  }
  .grid-box1 {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 1;
    grid-row-end: 2;
  }

  .grid-box2 {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
  }

  .grid-box3 {
    grid-column-start: 1;
    grid-column-end: 2;
    grid-row-start: 2;
    grid-row-end: 3;
  }

  .grid-box4 {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: 3;
  }
}
</style>
