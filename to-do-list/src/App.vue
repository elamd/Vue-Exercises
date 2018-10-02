
<template>
  <div id="app">
    <app-header v-bind:toDoList = "toDoList"></app-header>
    <app-list v-bind:toDoList = "toDoList"></app-list>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import List   from './components/List.vue';

export default {
  name: 'app',
  components: {
    'app-header':Header,
    'app-list':  List
  },
  data () {
    return {
      // description:'',
      // completed:false
      toDoList: [
      ]
    }
  },
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
