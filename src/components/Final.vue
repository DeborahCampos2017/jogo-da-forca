<template>
  <div class="final">
    <div :class="`final-texto ${etapa}`">
    {{texto}}
    </div>

    <button class="final-botao" v-on:click="jogarNovamente">Jogar Novamente</button>
  </div>
</template>

<script>
export default {
  name: "Final",
  props: {
    etapa: String,
    texto: String,
    jogarNovamente: Function,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style>
.final-texto{
  margin: 20px 0px;
  font-size: 30px;
  font-weight: bold;
  }
  .final-texto.enforcado{
    color:var(--color-text-error);
    }
    .final-texto.ganhador{
    color:var(--color-text-sucess);
    }
</style>