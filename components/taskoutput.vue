<template>
  <div id="output">
    <div id="pros">

      <ul>
        <p id="temp" v-if="pros.length == 0">your pros will list here ..
          
        </p>
        <li v-for="pro in pros" :key="pro">
          <span class="checkmark">✔</span> {{ pro }}
        </li>
      </ul>
    </div>

    <div id="cons">
      <ul>
        <p id="temp" v-if="cons.length == 0">your cons will list here ..

        </p>

        <li v-for="con in cons" :key="con">
          <span class="crossmark">✘</span> {{ con }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: ["pros", "cons"],
};
</script>

<style>
#output {
  display: flex;
  justify-content: space-between;
  width: 800px;
  margin: 0 auto;
  padding: 20px;
  background-color: #ffffff;
  border-radius: 10px;
}
#pros {
  width: 45%;
  background-color: #ade8ad;
  padding: 20px;
  margin-right: 10px;
  border-radius: 3px;
  border: 2px solid grey;
}
#pros ul {
  list-style-type: none;
  padding: 0;
}
#pros li {
  margin: 10px 0;
  padding: 10px;
  background-color: #e0ffe0;
  border-radius: 5px;
  display: flex;
  align-items: center;
}
.checkmark {
  color: green;
  margin-right: 10px;
}

#cons {
  width: 45%;
  background-color: #ecc4c4;
  padding: 20px;
  margin-left: 10px;
  border-radius: 3px;
  border: 2px solid grey;
}
#cons ul {
  list-style-type: none;
  padding: 0;
}
#cons li {
  margin: 10px 0;
  padding: 10px;
  background-color: #ffe0e0;
  border-radius: 5px;
  display: flex;
  align-items: center;
}
.crossmark {
  color: red;
  margin-right: 10px;
}
</style>
