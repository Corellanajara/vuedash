<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld asfkljas="afasflja" :textoculiao="var1"/>
  <Users color="blue" />
  <CardCustom :msg="stats" />
  
</template>

<script>

import axios from 'axios'
import Users from './components/Users.vue'
import HelloWorld from './components/HelloWorld.vue'
import CardCustom from './components/CardCustom.vue'

export default {
  name: 'App',
  data () {
    return {
      items: [
        { text: 'item 1' },
        { text: 'Item 2' }
      ],
      stats:null,
      var1: 'hola cabros'
    }
  }
  ,
  components: {
    HelloWorld,
    CardCustom,
    Users
  }
  ,
  mounted() {
    axios.get("https://pokeapi.co/api/v2/pokemon/charizard")
    .then(response => {
      console.log(response);
      this.stats = response.data.stats
      })
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
