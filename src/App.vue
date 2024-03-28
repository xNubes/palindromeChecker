<template>
    <div class="container">
      <h1>Palindrome Checker</h1>
      <div class="box">
      <input v-model="textInput" id="text-input"></input>
      <button @click="checkInput" id="check-btn">Check</button>
      <div id="result">{{ result }}</div>
    </div>
    <div class="box">
      <p>A word, phrase, or sequence that reads the same backwards as forwards, e.g. madam or nurses run.
</p>
    </div>
    <div class="rowContent">

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
body {
  height: 100%;

}
h1 {
  color: black;
  padding: 2rem;
  text-align: center;
}
p {
  color: #FAFAF5;
  margin-top: 2rem;
}
#result {
  color: #FAFAF5;
}
.container {

  background: #e8ebeb;
  min-width: 30rem;
  width: 75%;
  height: 100vh;
}
.box {
  height: auto;
  width: 20rem;
  padding: 2rem;
  margin: 2rem;
  display: flex;
  justify-content: center;
  flex-direction: column;
  background-color: #9D975C;
  margin: auto;
  border-radius: 2px;
  flex: 0 1 auto;
}
.rowContainer {
  flex: 1 1 auto;

}
button {
  margin: 1rem;
  width: fit-content;
  align-self: center;
  border-radius: 5px;
  padding: 0.2rem 1rem;
  background-color: #4F4A7D;
  color: #FAFAF5;
  border-color: #4F4A7D;
  border: none;
  
}

button:hover {
  box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24),0 17px 50px 0 rgba(0,0,0,0.19);

}

#result {
  align-self: center;
}

</style>