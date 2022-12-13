<template>
  <div id="app">
      <input v-model="username" placeholder="masukkan username..."/>
      <button v-on:click="masuk()">Masuk</button>
  </div>
</template>
<script>
import {db} from './db'

export default {
  name: 'App',
  data(){
    return{
      username:'',
    }
  },
  methods:{
    masuk(){
      db.collection('user').add({username: this.username});
      this.username = '';
    }
  }
}
</script>

<style>
#app{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top:200px;
  margin-bottom: 250px;
}


</style>