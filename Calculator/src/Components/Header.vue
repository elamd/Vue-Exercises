<template>
  <div>
    <input disabled id="output" type="text" v-bind:value="enumerateValues()"/>
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
    enumerateValues: function() {
      let total = '';
      this.inputData.forEach(v => {
        total += v;
      });
      return total;
    }
  }
}
</script>

<style>
  #output {
    width:100%;
    height:100px;
  }
</style>
