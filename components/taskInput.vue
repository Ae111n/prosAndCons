<template>
  <div id="app">
    <div class="input-container">
      <input
        id="input-field"
        type="text"
        placeholder="Enter item..."
        v-model="inputValue"
      />
      <div class="button-group">
        <button class="button pros-button" @click="$emit('addPro' , inputValue) , clearInput()" >
          add Pro
        </button>
        <button class="button cons-button" @click="$emit('addCon' , inputValue) , clearInput()" >
          add Con
        </button>
      </div>
    </div>

    <button id="clearBoards" @click="$emit('clearBoards')">clear boards</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: "",
    };
  },
  methods: {
    clearInput(){
this.inputValue=""
    }
  },
};
</script>

<style>
.input-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 0px;
}
#input-field {
  padding: 10px;
  width: 400px;
  border-top-right-radius: 5px;
  border-top-left-radius: 5px;
  border: 1px solid #bebebe;
  margin-bottom: 0px;
  text-align: center;
}
.button-group {
  display: flex;
  justify-content: center;
  width: 420px;
}
.button {
  padding: 10px;
  width: 50%;
  color: white;
  border: none;
  border-top-left-radius: 0px;
  border-top-right-radius: 0px;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;

  cursor: pointer;
  font-size: 1.2em;
}
.pros-button {
  background-color: #4caf50;
  border-bottom-right-radius: 0px;
}
.pros-button:hover {
  background-color: #45a049;
}
.cons-button {
  background-color: #f44336;
  border-bottom-left-radius: 0px;
}
.cons-button:hover {
  background-color: #e53935;
}

#clearBoards {
  width: 400px;
  display: block;
  margin: 0 auto;
  height: 30px;
}
#temp {
  opacity: 0.7;
  font-style: italic;
}
</style>
