<template>
  <div id="app">
    <header>
      <button @click.prevent="loadPicture()">Refresh</button>
    </header>
    <main>
      <section class="cards">
        <card v-for="(picture, index) in pictures" :key="index" :picture="picture" />
      </section>
    </main>
  </div>
</template>

<script>
import card from './components/card'
import axios from "axios";
export default {
  name: 'app',
  components:{
    card
  },
  data() {
    return {
      pictures:[]
    }
  },
  methods:{
    loadPicture(){
      axios.get('https://static.charly-e.com/apishib/wp-json/sh/v1/pictures').then(response => {
        this.pictures = response.data;
      })
    }
  },
  mounted() {
    this.loadPicture()
  }
}
</script>

<style>
body{
  margin:0;
  font-family: 'Montserrat', sans-serif;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin:0;
}
main{
  display: flex;
  justify-content: center;
}
header{
  background-color: #F7A000;
  width:100%;
  height:80px;
  display: flex;
  align-items: center;
}
button{
  margin-left:40px;
  background-color: #ffffff;
  border:none;
  width:160px;
  height:40px;
  border-radius: 10px;
  font-size:17px;
  color:#000;
  font-weight: bold;
  transition: 0.3s ease-in-out;
}

button:hover{
  background-color: #ffd585;
  cursor: pointer;
}

.cards{
  width:96%;
  display: flex;
  flex-wrap: wrap;
}
</style>
