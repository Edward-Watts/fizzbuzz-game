<template>
    <div >
        <h3>{{ message }}</h3>
        <p>{{ number }}</p>
        <Button @click="nextNumber()" text='Next Number' color='green' />
        <Button @click="reset()" text='Reset' color='red' />
    </div>
    
</template>

<script>
import Button from './Button'

export default {
  name: 'Playgame',

  data(){
      return {
          number: 1,
      }
  },

  computed: {
      message() {
          if(this.number%3 == 0 && this.number%5 == 0) return('FizzBuzz')
          else if(this.number%3 == 0) return('Fizz')
          else if(this.number%5 == 0) return('Buzz')
          else return this.number
      }
  },

  components: {
      Button
  },

  methods: {
      nextNumber() {
          this.number= this.number + 1
      },
      reset(){
          this.number = 1
      }
  }
}
</script>

<style>
h3 {
    background-color: gainsboro;
    display: flex;
    justify-content: center;
    border: 1px solid rgb(0, 0, 0);
  width: 80%;
  height: 40px;
  margin: 5px;
  padding: 20px 7px;
  font-size: 30px;    
}

p {
    display: flex;
    align-items: center;
    justify-content: center;
    border: 1px solid rgb(0, 0, 0);
  width: 80%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-weight: bold;
  font-size: 20px;
}
</style>