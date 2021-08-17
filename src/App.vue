<template>
  <div id="app">
   <h1> JOGO DA FORCA </h1>

   <section v-if="tela === 'inicio'" id="inicio">
     <formulario v-if="etapa === 'palavra'"
     title="Defina a palavra"
     button="Próximo"
     :action="setPalavra"/>
     

     <formulario v-if="etapa === 'dica'"
     title="Defina a dica"
     button="Iniciar jogo"
      :action="setDica"/>
    
   </section>

 <section v-if="tela === 'jogo'" id="jogo">
     <Jogo
     :erros = "erros"
     />
   </section>

  </div>
</template>

<script>
import './css/index.css';
import Jogo from './components/Jogo.vue';
import Formulario from './components/formulario.vue';

export default {
  name: 'App',
  data(){
    return{
      tela: 'inicio',
      etapa: 'palavra',
      palavra: '',
      dica: '',
      erros: '1',
    }
  },
  components: {
    Formulario,
    Jogo,
  },
  methods:{
    setPalavra: function(palavra){
      this.palavra = palavra;
      this.etapa = 'dica';
    },
    setDica: function(dica){
      this.dica = dica;
      this.tela = 'jogo';
      this.etapa = 'jogo';
    }
  },
   
  }

</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
