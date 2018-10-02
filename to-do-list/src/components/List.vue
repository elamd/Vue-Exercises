<template>
  <div class="grid-container">
    <template v-for="toDo,index in toDoList">
      <div>
        {{index + 1}}.
      </div>
      <div>
        {{toDo.description}}
      </div>
      <div>
        <input type="checkbox" v-on:click="markComplete(index)"> Completed
      </div>
    </template>
  </div>
</template>

<script>
export default {
  props: ['toDoList'],
  data () {
    return {
    }
  },
  methods: {
    markComplete: function(index) {
      if(!this.toDoList[index].markComplete) {
        this.toDoList.splice(index,1);
      }
    }
  }
}
</script>

<style>
  .grid-container {
    display: grid;
    grid-template-columns: auto auto auto
  }
</style>
