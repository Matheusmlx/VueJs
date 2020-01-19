<template>
  <!-- // Propriedade pode ser controlada como qualquer outro atributo -->
  <div class="componente">
    <h2>As Informações de Usuário</h2>
    <p>Vários detalhes...</p>
    <p>
      Nome do Usuario
      <strong>{{inverterNome()}}</strong>
    </p>
    <p>
      Idade do Usuario
      <strong>{{idade}}</strong>
    </p>
    <button @click="reiniciarNome">Reiniciar Nome</button>
  </div>
</template>

<script>
export default {
  props: {
    //pode ser tratado como sendo uma string ou array
    nome: [String, Array],
    idade: Number
  },
  methods: {
    inverterNome() {
      return this.nome
        .split("")
        .reverse()
        .join("");
    },
    reiniciarNome() {
      this.nome = "Pedro";
      this.$emit("nomeMudou", this.nome);
    }
  }
};
</script>

<style scoped>
.componente {
  flex: 1;
  background-color: #ec485f;
  color: #fff;
}
</style>

