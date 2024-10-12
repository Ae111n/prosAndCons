<template>
  <div>
   
    <TaskInput
      @addPro="addPro"
      @addCon="addCon"
      @clearBoards="clearBoards"
    ></TaskInput>
     <taskoutput :pros="pros" :cons="cons"></taskOutput>

    <p>{{ newPoint }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {

      pros: [],
      cons: [],
    };
  },
  methods: {
    addPro(proValue) {
      if(proValue.trim()!==""){
         this.pros.push(proValue)
      }
      console.log(proValue);
    
    },
    addCon(conValue) {
      if(conValue.trim()!==""){
             this.cons.push(conValue)
      }
 
    },

    clearBoards() {
      if (this.pros.length > 0 || this.cons.length > 0) {
        this.pros = [];
        this.cons = [];
        this.saveToLocalStorage();
      }
    },
    saveToLocalStorage() {
      localStorage.setItem("pros", JSON.stringify(this.pros));
      localStorage.setItem("cons", JSON.stringify(this.cons));
    },
    loadFromLocalStorage() {
      const savedPros = localStorage.getItem("pros");
      const savedCons = localStorage.getItem("cons");

      if (savedPros) {
        this.pros = JSON.parse(savedPros);
      }
      if (savedCons) {
        this.cons = JSON.parse(savedCons);
      }
    },
  },
  mounted() {
    this.loadFromLocalStorage();
  },
};
</script>
