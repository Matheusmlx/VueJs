<template>
  <div class="contador">
    <span id="contador">{{contador}}</span>
    <button class="botaoContador" @click="adicionar">+</button>
    <button class="botaoContador" @click="subtrair">-</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contador: 0
    };
  },
  methods: {
    adicionar() {
      this.contador++;
    },
    subtrair() {
      this.contador--;
    }
  }
};
</script>

<style scoped>
/* scoped serve para deixar o estilo apenas no escopo do componente */
#contador {
  font-size: 45px;
}
button {
  height: 30px;
  width: 30px;
  border-radius: 15px;
  background: coral;
  color: #fff;
  margin-left: 10px;
  outline: none;
}
</style>