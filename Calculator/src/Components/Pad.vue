<template>
  <div class="grid-container">
    
    <div class="button">
      <button v-on:click="addNum(7)">7</button>
    </div>
    <div class="button">
      <button v-on:click="addNum(8)">8</button>
    </div>
    <div class="button">
      <button v-on:click="addNum(9)">9</button>
    </div>
    <div class="button plus">
      <button v-on:click="addNum('+')">+</button>
    </div>
  
    <div class="button">
      <button v-on:click="addNum(4)">4</button>
    </div>
    <div class="button">
      <button v-on:click="addNum(5)">5</button>
    </div>
    <div class="button">
      <button v-on:click="addNum(6)">6</button>
    </div>
    <div class="button">
      <button v-on:click="addNum('-')">-</button>
    </div>
    <div class="button">
      <button v-on:click="addNum(1)">1</button>
    </div>
    <div class="button">
      <button v-on:click="addNum(2)">2</button>
    </div>
    <div class="button">
      <button v-on:click="addNum(3)">3</button>
    </div>
    <div class="button enter">
      <button v-on:click="addNum('ENTER')">ENTER</button>
    </div>
    <div class="button zero">
      <button v-on:click="addNum(0)">0</button>
    </div>
    <div class="button">
      <button v-on:click="addNum('.')">.</button>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['inputData'],
    data () {
      return {
      }
    },
    methods: {
      addNum: function(num) {

        if(Number.isInteger(num) || num == '.') {
          this.inputData.push( this.inputData.length == 0 ? num.toString() : this.inputData.pop() + num.toString() );
        }
        else if(num === 'ENTER'){
          let total = 0;
          for(let i=0;i<this.inputData.length;i++) {
            console.log(total);
            let val = this.inputData[i];
            if(val == '+') {
              total += Number.parseFloat(inputData[i++]);
            }
            else if(val == "-") {
              total -= Number.parseFloat(inputData[i++]);
            }
            total += Number.parseFloat(val);
          }
          this.inputData.length = 0;
          this.inputData.push( [total] );
        }
        else {
          this.inputData.push(num);
        }
      }
    }
  }
</script>

<style>
  .grid-container {
    display:grid;
    grid-template-columns: auto auto auto auto;
    grid-template-rows: auto auto auto auto;
  }
  .button {
    background-color: gray;
    text-align: center;
  }
  .zero {
    grid-column: 1 / span 2;
    grid-row: 4;
  }
  .enter {
    grid-row: 3 / span 2;
    grid-column: 4;
  }
  button {
    width:100%;
    height:100%;
  }
</style>
