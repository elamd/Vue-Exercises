<template>
<div>
  <div class="grid-container"  v-on:click="mark">
    
    <div class="box" id="1"></div>
    <div class="box" id="2"></div>
    <div class="box" id="3">
    </div>

    <div class="box" id="4"></div>
    <div class="box" id="5"></div>
    <div class="box" id="6"></div>

    <div class="box" id="7"></div>
    <div class="box" id="8"></div>
    <div class="box" id="9"></div>
  
  </div>
  <p><button v-on:click="start" id="startButton">Start</button></p>
</div>
</template>

<script>

export default {
  props: ['gameData'],
  data () {
    return {
      currentMoves: ['','']
    }
  },
  methods: {
    start: function(event) {
      let button = document.getElementById(event.target.id);
      this.gameData.started = !this.gameData.started;
      if( this.gameData.started) {
        button.innerText = 'Cancel';
      }
      else {
        button.innerText = 'Start';
        let elements = document.getElementsByClassName('box');
        for(let i=0; i < elements.length; i++) {
          elements.item(i).textContent = '';
        }
      }
    },
    mark: function( event ) {
      if(!this.gameData.started) 
        return;
      let mark = '';
      this.gameData.turn == 'X' ? this.gameData.turn = 'O' : this.gameData.turn = 'X';
      document.getElementById(event.target.id).textContent = this.gameData.turn;
      this.gameData.turn == 'X' ? currentMoves[0] += event.target.id.toString() : currentMoves[1] += event.target.id.toString();

      let winningString = '';
      // Check for great succcess!
      this.currentMoves.forEach( currentMove => {
        this.gameData.moves.forEach( move => {
          // Check if any of the winning moves are in the currentMove string.
          if( move.search(currentMove) > -1) {
            console.log('winner');
          }
        });
      })
    }
  }
}
</script>

<style>
  .grid-container {
    display:grid;
    grid-template-columns: repeat(3,1fr);
    grid-auto-rows: 200px;
    width: 50%;
    min-width: 500px;
    margin: auto;
    grid-gap:3px;
    box-shadow: 10px 10px 15px;
  }

  .grid-container div {
    border:1px black solid;
    display:flex;
    align-items:center;
    justify-content: center;
    text-overflow: ellipsis;
    overflow:hidden;
    font-size: 10em;
  }

  .grid-container div:nth-child(even) {
    background: rgb(162, 210, 255);
  }

  .grid-container div:nth-child(odd) {
    background:rgb(93, 169, 255);
  }

  button {
    padding:10px;
    box-shadow: 10px 10px 15px;
  }
</style>
