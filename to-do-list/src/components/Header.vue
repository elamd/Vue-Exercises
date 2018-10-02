
<template>
  <div>
    <p>
      Item: <input type="text" v-model="toDo"/> <button v-on:click="addToDo()">Add</button>
    </p>
  </div>
</template>

<script>
export default {
  props: ['toDoList'],
  data () {
    return {
      toDo:''
    }
  },
  methods: {
    addToDo: function() {
      this.toDoList.push({
        description:this.toDo,
        completed:false
      });
    }
  }
}
</script>

<style>

</style>
