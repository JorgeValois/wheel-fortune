<template>
  <div id="app">
    <div id="initialScreen"> 
      <div id="container">
      <section>
      <img id="title" src="./assets/title.png"/>
      <button id="testeSuaSorteBt" v-on:click="changeToWheel">Teste Sua Sorte!</button>
      </section>
      </div>
     </div> 
    <div id="wheelScreen">

      <div id="container">
        <section>
        <h1>Teste Sua Sorte!</h1>
          <button id="girarRoleta" v-on:click="spinWheel">Girar</button>
          <button id="voltar" v-on:click="changeToInitialScreen">Voltar</button>
        </section>
        <section>
          <img id="pino" width="45" src="./assets/pino.png"/>
          <img id="roleta" width="445" src="./assets/roleta.png"/>
        </section>
        
      </div>
    </div>
  </div>
</template>

<script>
  export default {
  name: 'app',
  methods: {
    changeToWheel: function(){
      var initialScreen = document.querySelector("#initialScreen");
      var wheelScreen = document.querySelector("#wheelScreen");

      initialScreen.style.display = 'none';
      wheelScreen.style.display = 'flex';
    },
    changeToInitialScreen: function(){
      var initialScreen = document.querySelector("#initialScreen");
      var wheelScreen = document.querySelector("#wheelScreen");

      initialScreen.style.display = 'block';
      wheelScreen.style.display = 'none';
    },

    spinWheel: function(){
      var min = Math.ceil(12);
      var max = Math.floor(20);
      var result = Math.floor(Math.random() * (max - min + 1)) + min;
      
       document.querySelector("#roleta").style.transform = 'rotate('+result*937+'grad)';
       document.querySelector("#roleta").style.transition = '2.5s ease';

    }
  },
  data () {
    return {
      msg: 'Hello, World!'
    }
  }
}
 
</script>


<style>
*{
    margin: 0;
    padding: 0;
    outline: 0;
    box-sizing: border-box;
}

@font-face {
  font-family: casino;
  src: url("./assets/CasinoFlatShadow-Italic.ttf") format("opentype");
}

h1 {
  color: #ffb754;
  -webkit-text-stroke-width: 1px; /* largura da borda */
  -webkit-text-stroke-color: #241532; /* cor da borda */
  font-size: 75px ;
  font-family: casino;
}

button{
    background-color: #241532;
  border: 1px solid #ffb754;
  -webkit-text-stroke-width: 1px; /* largura da borda */
  -webkit-text-stroke-color: #241532; /* cor da borda */
  color: #ffb754;
  padding: 15px 32px;
  text-align: center;
  display: inline-block;
  font-family: casino;
  font-size: 35px;
  border-radius: 5px;
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2), 0 6px 20px 0 rgba(0,0,0,0.19);
  cursor: pointer;
  margin: 50px;
  transition: filter 0.2s;
  line-height: 30px;

  
}

button:hover{
        filter:brightness(90%)
}



#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
  background: #000;
}
#initialScreen{
  background: url("./assets/background.gif") no-repeat center;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  width: 100%;
  height: 100vh;
  margin: 0 auto;


}

#testeSuaSorteBt{
    margin: 15vh 0 0 0 ;
  }

#wheelScreen{
  background: radial-gradient( #481D07, #000);
  display: none;
  width: 100%;
  height: 100vh;
  margin: 0 auto;

  align-items: center;
  justify-content: center;
}

#container{
   width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

#container section{
  
  max-width: 450px;
  margin: 0 auto;
}

#pino{
  margin: 200px 0;
  position: absolute;
  z-index: 20;
}

#roleta{
  position: relative;
  margin: auto;
}

</style>
