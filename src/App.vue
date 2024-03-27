<template>
    <div class="container">
      <h1>Palindrome Checker</h1>
      <div class="box">
      <input v-model="textInput" id="text-input"></input>
      <button @click="checkInput" id="check-btn">Check</button>
      <div id="result">{{ result }}</div>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      textInput: '',
      result: ''
    };
  },
  methods: {
    checkInput() {
      const lowercaseText = this.textInput.toLowerCase().trim();
      const regex = /[^a-z0-9]/g;
      const cleanText = lowercaseText.replace(regex, '');
      const reversedText = cleanText.split('').reverse().join('');

      if (lowercaseText === "") {
        this.result = "Please input a value";
      } else if (cleanText === reversedText) {
        this.result = lowercaseText + " is a palindrome";
      } else {
        this.result = lowercaseText + " is not a palindrome";
      }
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  flex-direction: column;
  flex-wrap: wrap;
  align-content: center;
}
.box {
  height: auto;
  width: 20rem;
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin: auto;
}
button {
  margin: 1rem;
  width: fit-content;
  align-self: center;
}

#result {
  align-self: center;
}
@media (min-width: 1024px) {

}
@media (prefers-color-scheme: dark) {

} 
/* Add your scoped styles here if needed */
</style>