<template>
  <div id="app">
    <app-pad    v-bind:inputData="inputData"></app-pad>
    <app-output v-bind:inputData="inputData"></app-output>
  </div>
</template>

<script>

import Pad    from './components/Pad.vue';
import Output from './components/Output.vue';

export default {
  name: 'app',
  components: {
    'app-pad':Pad,
    'app-output':Output
  },
  data () {
    return {
      inputData:  []
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
