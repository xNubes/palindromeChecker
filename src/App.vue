<template>
  <div class="box">
    <input v-model="textInput" id="text-input"></input>
    <button @click="checkInput" id="check-btn">Check</button>
    <div id="result">Result: {{ result }}</div>
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
/* Add your scoped styles here if needed */
</style>