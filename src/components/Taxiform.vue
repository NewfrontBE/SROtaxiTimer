<template>
<!--Player 1 -->
  <form v-bind:class="{taxiRunning: player1Status, taxiStopped: !player1Status}">
      <label>Player 1:</label>
      <input type="text" v-model="player1Name" placeholder="Name">
      <label>Time left:</label>
      <input type="number" v-model="player1TimeLeft">
      <button @click="startP1" :disabled="player1Status" class="button startbutton">Start</button>
      <button @click="add15P1" class="button">+ 15min</button>
      <button @click="add30P1" class="button">+ 30min</button>
      <button @click="add60P1" class="button">+ 60min</button>
      <button @click="resetP1" class="button resetbutton">RESET</button>
  </form>

<!--Player 2 -->
    <form v-bind:class="{taxiRunning: player2Status, taxiStopped: !player2Status}">
      <label>Player 2:</label>
      <input type="text" v-model="player2Name" placeholder="Name">
      <label>Time left:</label>
      <input type="number" v-model="player2TimeLeft">
      <button @click="startP2" :disabled="player2Status" class="button startbutton">Start</button>
      <button @click="add15P2" class="button">+ 15min</button>
      <button @click="add30P2" class="button">+ 30min</button>
      <button @click="add60P2" class="button">+ 60min</button>
      <button @click="resetP2" class="button resetbutton">RESET</button>
  </form>

<!--Player 3 -->
    <form v-bind:class="{taxiRunning: player3Status, taxiStopped: !player3Status}">
      <label>Player 3:</label>
      <input type="text" v-model="player3Name" placeholder="Name">
      <label>Time left:</label>
      <input type="number" v-model="player3TimeLeft">
      <button @click="startP3" :disabled="player3Status" class="button startbutton">Start</button>
      <button @click="add15P3" class="button">+ 15min</button>
      <button @click="add30P3" class="button">+ 30min</button>
      <button @click="add60P3" class="button">+ 60min</button>
      <button @click="resetP3" class="button resetbutton">RESET</button>
  </form>

<!--Player 4 -->
    <form v-bind:class="{taxiRunning: player4Status, taxiStopped: !player4Status}">
      <label>Player 4:</label>
      <input type="text" v-model="player4Name" placeholder="Name">
      <label>Time left:</label>
      <input type="number" v-model="player4TimeLeft">
      <button @click="startP4" :disabled="player4Status" class="button startbutton">Start</button>
      <button @click="add15P4" class="button">+ 15min</button>
      <button @click="add30P4" class="button">+ 30min</button>
      <button @click="add60P4" class="button">+ 60min</button>
      <button @click="resetP4" class="button resetbutton">RESET</button>
  </form>

<!--Player 5 -->
    <form v-bind:class="{taxiRunning: player5Status, taxiStopped: !player5Status}">
      <label>Player 5:</label>
      <input type="text" v-model="player5Name" placeholder="Name">
      <label>Time left:</label>
      <input type="number" v-model="player5TimeLeft">
      <button @click="startP5" :disabled="player5Status" class="button startbutton">Start</button>
      <button @click="add15P5" class="button">+ 15min</button>
      <button @click="add30P5" class="button">+ 30min</button>
      <button @click="add60P5" class="button">+ 60min</button>
      <button @click="resetP5" class="button resetbutton">RESET</button>
  </form>

<!--Player 6 -->
    <form v-bind:class="{taxiRunning: player6Status, taxiStopped: !player6Status}">
      <label>Player 6:</label>
      <input type="text" v-model="player6Name" placeholder="Name">
      <label>Time left:</label>
      <input type="number" v-model="player6TimeLeft">
      <button @click="startP6" :disabled="player6Status" class="button startbutton">Start</button>
      <button @click="add15P6" class="button">+ 15min</button>
      <button @click="add30P6" class="button">+ 30min</button>
      <button @click="add60P6" class="button">+ 60min</button>
      <button @click="resetP6" class="button resetbutton">RESET</button>
  </form>

</template>

<script>
export default {
    data(){
        return {
            player1Name: '',
            player1TimeLeft: 5,
            player1Status: false,
            player2Name: '',
            player2TimeLeft: 5,
            player2Status: false,
            player3Name: '',
            player3TimeLeft: 5,
            player3Status: false,
            player4Name: '',
            player4TimeLeft: 5,
            player4Status: false,
            player5Name: '',
            player5TimeLeft: 5,
            player5Status: false,
            player6Name: '',
            player6TimeLeft: 5,
            player6Status: false,
            timer: null,
            timer2: null,
            timer3: null,
            timer4: null,
            timer5: null,
            timer6: null
        }
    },
    methods: {
        startP1(){
            this.player1Status = true
            this.timer = setInterval(() => {
                this.player1TimeLeft -= 1
                console.log(this.timer)
                if(this.player1TimeLeft === 0){
                    this.player1Status = false
                    clearInterval(this.timer)
                }
            }, 60000)
        },
        add15P1(){
            this.player1TimeLeft += 15
        },
        add30P1(){
            this.player1TimeLeft += 30
        },
        add60P1(){
            this.player1TimeLeft += 60
        },
        resetP1(){
            this.player1Name = '',
            this.player1Status = false,
            this.player1TimeLeft = 60,
            clearInterval(this.timer)
        },
        startP2(){
            this.player2Status = true
            this.timer2 = setInterval(() => {
                this.player2TimeLeft -= 1
                if(this.player2TimeLeft === 0){
                    this.player2Status = false
                    clearInterval(this.timer2)
                }
            }, 60000)
        },
        add15P2(){
            this.player2TimeLeft += 15
        },
        add30P2(){
            this.player2TimeLeft += 30
        },
        add60P2(){
            this.player2TimeLeft += 60
        },
        resetP2(){
            this.player2Name = '',
            this.player2Status = false,
            this.player2TimeLeft = 60,
            clearInterval(this.timer2)
        },
        startP3(){
            this.player3Status = true
            this.timer3 = setInterval(() => {
                this.player3TimeLeft -= 1
                if(this.player3TimeLeft === 0){
                    this.player3Status = false
                    clearInterval(this.timer3)
                }
            }, 60000)
        },
        add15P3(){
            this.player3TimeLeft += 15
        },
        add30P3(){
            this.player3TimeLeft += 30
        },
        add60P3(){
            this.player3TimeLeft += 60
        },
        resetP3(){
            this.player3Name = '',
            this.player3Status = false,
            this.player3TimeLeft = 60,
            clearInterval(this.timer3)
        },
        startP4(){
            this.player4Status = true
            this.timer4 = setInterval(() => {
                this.player4TimeLeft -= 1
                if(this.player4TimeLeft === 0){
                    this.player4Status = false
                    clearInterval(this.timer4)
                }
            }, 60000)
        },
        add15P4(){
            this.player4TimeLeft += 15
        },
        add30P4(){
            this.player4TimeLeft += 30
        },
        add60P4(){
            this.player4TimeLeft += 60
        },
        resetP4(){
            this.player4Name = '',
            this.player4Status = false,
            this.player4TimeLeft = 60,
            clearInterval(this.timer4)
        },
        startP5(){
            this.player5Status = true
            this.timer5 = setInterval(() => {
                this.player5TimeLeft -= 1
                if(this.player5TimeLeft === 0){
                    this.player5Status = false
                    clearInterval(this.timer5)
                }
            }, 60000)
        },
        add15P5(){
            this.player5TimeLeft += 15
        },
        add30P5(){
            this.player5TimeLeft += 30
        },
        add60P5(){
            this.player5TimeLeft += 60
        },
        resetP5(){
            this.player5Name = '',
            this.player5Status = false,
            this.player5TimeLeft = 60,
            clearInterval(this.timer5)
        },
        startP6(){
            this.player6Status = true
            this.timer6 = setInterval(() => {
                this.player6TimeLeft -= 1
                if(this.player6TimeLeft === 0){
                    this.player6Status = false
                    clearInterval(this.timer6)
                }
            }, 60000)
        },
        add15P6(){
            this.player6TimeLeft += 15
        },
        add30P6(){
            this.player6TimeLeft += 30
        },
        add60P6(){
            this.player6TimeLeft += 60
        },
        resetP6(){
            this.player6Name = '',
            this.player6Status = false,
            this.player6TimeLeft = 60,
            clearInterval(this.timer6)
        }
    }
}
</script>

<style>
form {
    max-width: 600px;
    margin: 10px auto;
    background:#fff;
    text-align: left;
    padding: 10px;
    border-radius: 10px;
}
.taxiRunning {
    background:#B7B7A4;
}
.taxiStopped {
    background:#CB997E;
}
label {
    color: #000;
    margin: 0 10px 0 5px;
    font-size: 0.7em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input {
    display:inline;
    padding: 10px 6px;
    max-width: 27%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
}
.button {
    margin: 15px 5px 0 0;
    background: white;
    padding: 10px;
    border: 1px solid #FFE8D6;
}
.startbutton {
    margin:0 0 0 5px;
    background: #6B705C;
    font-weight: 600;
    color:white;
}
.resetbutton {
    margin: 0 0 0 50px;
    background: #573d2f;
    color: white;
}
</style>