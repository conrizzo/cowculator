

<template>
  
      
     
  <div class="grid-container cow-image">
    
    <button
      class="grid-item"
      @click="
        addNumber();">
    
      1
    </button>
    <button
      class="grid-item"
      @click="
        addNumberTwo();">
      2
    </button>
    <button
      class="grid-item"
      @click="
        addNumberThree();">
    
      3
    </button>
    <button
      class="grid-item"
      @click="
        addNumberFour();">
    
      4
    </button>
    <button
      class="grid-item"
      @click="
        addNumberFive();">
    
      5
    </button>
    <button
      class="grid-item"
      @click="
        addNumberSix();">
    
      6
    </button>
    <button
      class="grid-item"
      @click="
        addNumberSeven();">
    
      7
    </button>
    <button
      class="grid-item"
      @click="
        addNumberEight();">
 
      8
    </button>
    <button
      class="grid-item"
      @click="
        addNumberNine();">
      9
    </button>
    <button
      class="grid-item"
      @click="
        addMultiplication();"
    >
      *
    </button>
    <button
      class="grid-item"
      @click="
        addDivision();
        
      "
    >
      ÷
    </button>
    <button class="grid-item" @click="addNumberZero()">0</button>

    <!-- override styling to fit in more text for the element below -->
    <button
      class="grid-item"
      @click="
        addSubtraction();
        
      "
    >
      -
    </button>
    <button
      class="grid-item"
      @click="
        addAddition();      
      "
    >
     +
    </button>
    <button
      class="grid-item"
      @click="
        addMoo();        
      "
    >
      Moo
    </button>
  </div>
  
  <div style="margin-bottom:5px;">   
        <button class="button-35"  @click="clearField">
  Reset
</button>   
      <button class="button-35" style="margin-left: 5px" @click="cowculate(), mooDialogue()">Cowculate</button>


</div>
  <div style="padding:20px; margin-bottom: 50px;">
   
    <h2  style="padding-top: 5px;
        padding-bottom: 3px;
        margin-top: 20px;
        
        font-size: 20px;
        
        position: absolute;
        left: 0; 
  right: 0; 
  margin-left: auto; 
  margin-right: auto; 
        color: rgb(200,200,200)">
      {{ expression }}<span v-if="showText"> = {{result}} <br> Number of Moos: {{ moos }} </span></h2>
      <input style="width: 268px; margin-bottom: 7px" v-model="expression" type="text"/>
    
    
  </div>
</template>
<script>
export default {
  data() {
    return {
      numbers: [],
      showText: false,
      expression: "",
      moos: null,
      result: null,
    };
  },

  methods: {
    cowculate() {
      /* Cow Moo cowculations */
      let str = this.expression
      let count = 0;

        while (str.indexOf("Moo") !== -1) {
          count++;
          str = str.replace("Moo", "");
        }
        this.moos = count 
        console.log("Number of 'Moo' occurrences:", count);
        console.log("String after removing 'Moo':", str);
      try {
        this.result = eval(str);
        
        
      } catch (error) {
        this.result = null;
      }
    },
    addNumber() {
      this.expression+=1;
    },
    addNumberTwo() {
      this.expression+=2;
    },
    addNumberThree() {
      this.expression+=3;
    },
    addNumberFour() {
      this.expression+=4;
    },
    addNumberFive() {
      this.expression+=5;
    },
    addNumberSix() {
      this.expression+=6;
    },
    addNumberSeven() {
      this.expression+=7;
    },
    addNumberEight() {
      this.expression+=8;
    },
    addNumberNine() {
      this.expression+=9;
    },
    addNumberZero() {
      this.expression+=0;
    },
    addMoo() {
      this.expression+="Moo";
    },
    mooDialogue() {
      this.showText = true;
    },
    addAddition() {
      this.expression+="+";
    },
    addSubtraction() {
      this.expression+="-";
    },
    addMultiplication() {
      this.expression+="*";
    },
    addDivision() {
      this.expression+="/";
    },
    /* Reset the array - if some error happens or want to restart */
    clearField() {
      this.numbers = [];
      this.expression = "";
      this.showText = false;
      this.result = null;
    },
  },

};
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: auto auto auto;
  background-color: #fff;
  padding: 10px;
  max-width: 250px;
  margin-left: auto;
  margin-right: auto;

  margin-bottom: 10px;


  
}
.grid-item {
  background-color: rgba(30, 30, 30, 0.7);
  border: 1px solid rgba(0, 0, 0, 1);
  padding: 20px;
  font-size: 20px;
  text-align: center;
  margin: 2px;
  border-radius: 12px;
  width:80px;
  color: rgb(218, 218, 218,0.9);
  
  
}
.grid-item:hover {
  background-color: rgba(186, 186, 186, 0.318);
}
</style>