<template>
    <div class="container">
        <Header title="FizzBuzz" :playerName="player" />
        <Startgame v-if="!gameStarted" @play-game="playGame" />
        <Playgame v-else @end-game="endGame" />
    </div>
</template>

<script>
import Header from './components/Header'
import Startgame from './components/Startgame'
import Playgame from './components/Playgame'

export default {
    name: 'App',

    components: {
        Header,
        Startgame,
        Playgame
    },

    data: function() {

      return {
         gameStarted: false,
         player: null
      }
    },

    methods: {
        playGame(event){
          this.player = event.name
          this.gameStarted = true
        },

        endGame() {
          if(confirm('Are you sure')) {
          this.gameStarted = false
          this.player = null
          }
        }
    }
}
</script>

<style>

.container {
    font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  color: #2c3e50;
  margin-top: 60px;
  text-align: inherit;
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 7px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 20px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}
</style>