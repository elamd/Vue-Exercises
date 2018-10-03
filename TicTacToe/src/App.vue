<template>
  <div id="app">
    <app-panel v-bind:gameData="gameData"></app-panel>
  </div>
</template>

<script>

  import Panel from './components/Panel.vue';
  
  export default {
    name: 'app',
    components: {
      'app-panel':Panel
    },
    data () {
      return {
        gameData: {
          started:false,
          moves:['123',
                 '456',
                 '789',
                 '147',
                 '258',
                 '369',
                 '159', // Diagonal 
                 '357'  // Diagonal
                ],
          turn: 'X'
        }
      }
    }
  }
</script>

<style>
body {
  background-image: radial-gradient(circle, #2342, black);
  background-repeat: no-repeat;
  background-position:center;
  background-size:cover;
  height:100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50; 
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
