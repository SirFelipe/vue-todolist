<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    TO DO LIST:
    <Entrada v-on:mudou="digitou"/>
    <br>
    <Button texto="Inserir" classe="btn btn-primary" fundo="" v-on:clicou="this.inserir"/>
    <br>
    <div :key="indice" v-for="(valor, indice) in lista">
      <a style="{color: #b3e6ff}" href="#" v-on:click="remover(indice)">{{valor}}</a>
    </div>
  </div>
</template>

<script>
import Entrada from './components/Entrada.vue'
import Button from './components/Button.vue'

export default {
  name: 'app',
  components: {
    Entrada,
    Button
  },
  data(){
    return { 
      valor: "",
      lista: []
    }
  },
  methods:{
    digitou(txt){
      this.valor = txt;
    },
    remover(idx){
                //MÉTODO MAIS BIXÃO QUE EXISTE
                //O BIXO REMOVE E ADICIONA
                //     Indice, Quantidade a ser removida, ["Adicionar1","Adicionar2"]
      this.lista.splice(idx, 1);
    },
    inserir(){
      this.lista.push(this.valor);
    }
  }
}
</script>
<style lang="scss">
      @import '../node_modules/bootstrap/scss/bootstrap.scss';

      #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
      }
</style>
