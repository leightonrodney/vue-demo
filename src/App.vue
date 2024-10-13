<script setup>

const greeting = 'Welcome to MTM6407 - VueJS';

const users = [
  {
    name: 'John Doe',
    hobbies: ['Running', 'Painting', 'Playing Piano']
  },
  {
    name: 'Mary Sue',
    hobbies: ['Glamping', 'Pokemon Go', 'Reading']
  },
  {
    name: 'Mark James',
    hobbies: ['CS Go', 'Call of Duty', 'Minecraft']
  },
  {
    name: 'Max Jills',
    hobbies: ['Reading', 'Walking', 'Writing Poetry']
  }
];

const playerStats = {
  lives: 3,
  stamina: 99,
  hp: 50,
  manna: 40,
  durability: 'STRONG',
};

/*

const showCount = () => {
  setInterval(() => { console.log(count++) }, 1000)
}
  
*/

console.log(users)

const studentId = 16604;

let count = 0;

const linkText = "https://youtube.com/";
const linkText2 = "https://yahoo.com/";

const bmw = "https://images.unsplash.com/photo-1653047256226-ab0d16c758d5?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D";
const imgAlt = "Image of a red sportscar.";
const imgWidth = "700";

const userBalance = 0;
const balanceMin = 400;
const isLoggedIn = true;


</script>

<template>

  <!-- <a v-bind:href="linkText2" target="_blank">Click me</a> -->

  <!-- <img :src="bmw" :alt="imgAlt" :width="imgWidth" /> -->

  <div v-if="isLoggedIn" class="homepage">

    <h1>Banking App</h1>

    <div v-if="userBalance > balanceMin" class="special-offer">
      <h2>Special Offer Available for you!</h2>
      <button>Learn More</button>
    </div>
    <h2>Your balance is: ${{ userBalance.toFixed(2) }}</h2>

  </div>
  <div v-else class="login">
    <form>
      <input type="email" placeholder="Username" />
      <br/>
      <input type="password" placeholder="Password" />
      <br/>
      <button>Login</button>
    </form>
  </div>

  <ul>
    <li v-for="user in users">
      {{ user.name }}
      (Hobby: <span class="hobby" v-for="hobby in user.hobbies">{{ hobby }}</span> )
    </li>
  </ul>

  <h3>Player Stats</h3>
  <ul class="player-stats">
    <li v-for="(value, stat) in playerStats">
      <strong>{{ stat.toString().toUpperCase() }}</strong>: {{ value }}
    </li>
  </ul>

</template>

<style scoped>

* {
  font-family: 'Arial', sans-serif;
}

h1 {
  color: green;
  font-size: 60px;
  font-family: serif;
}

.hobby:after {
  content: ', ';
}

.player-stats {
  list-style: none;
}

</style>
