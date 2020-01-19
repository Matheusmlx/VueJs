<template>
  <div class="componente">
    <h2>Alterar os Dados de Usuário</h2>
    <p>Edite as informações</p>
    <p>
      Idade é
      <strong>{{idade}}</strong>
    </p>
    <button @click="mudarIdade">Alterar Idade</button>
  </div>
</template>

<script>
export default {
  props: { idade: Number },
  methods: {
    mudarIdade() {
      this.idade = 21;
      this.$emit("idadeAlterada", this.idade);
    }
  }
};
</script>

<style scoped>
.componente {
  flex: 1;
  background-color: #98b99a;
  color: #fff;
}
</style>
