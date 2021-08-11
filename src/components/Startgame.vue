<template>
    <div class= "start">
        <div class="control">
        <input type="text" v-model="text" name="text" placeholder="Enter player name" />
        </div>
        <Button @click="onSubmit" text="Start" color="black" />
    </div>
</template>

<script>
import Button from './Button'

export default {
    name: 'Startgame',

    components: {
        Button
    },

    data() {
        return {
            text: '',
        }
    },

    methods: {
       
        onSubmit() {
            console.log(this.text)
            if(!this.text) {
                alert('Please enter player name')
            
            }

            const newPlayer = {
                id: Math.floor(Math.random() * 1000),
                name: this.text,
            }
            this.$emit('play-game', newPlayer)
            
            this.text = ''
        }
    }
}
</script>

<style scoped>
.start {
  margin-bottom: 40px;
}

.control {
  margin: 20px 0;
}

.control input {
  width: 80%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}

</style>