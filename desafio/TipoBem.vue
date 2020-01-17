<template>
  <v-form>
    <div class="az-form-content">
      <v-container fluid class="grey lighten-5">
        <v-row class="lighten-5" align="center" justify="center">
          <v-col cols="4">
            <p style="color:grey">Selecione o tipo de bem intangivel:</p>
          </v-col>
        </v-row>
        <v-row justify="center">
          <v-col cols="12" class="ma-3">
            <v-row align="center" justify="center" class="lighthen-5">
              <v-col cols="4" v-for="bem in bens" :key="bem.id">
                <v-card
                  outlined
                  tile
                  class="ma-3 pa-3"
                  hover
                  :style="bem.style"
                  @click="selecionarBem(bem),bemSelecionad=true"
                >
                  <v-row justify="center">
                    <v-icon :color="bem.iconStyle" large>{{bem.icon}}</v-icon>
                  </v-row>
                  <v-row class="mt-3" justify="center">{{bem.nome}}</v-row>
                </v-card>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </v-form>
</template>

<script>
export default {
  name: "TipoBemEdicao",
  data() {
    return {
      bemSelecionado: Boolean,
      estiloBemSelecionado: "",
      bens: [
        {
          id: 1,
          nome: "SOFTWARES",
          icon: "mouse",
          style: "color:grey"
        },
        {
          id: 2,
          nome: "DIREITOS AUTORAIS",
          icon: "copyright",
          iconStyle: "",
          style: "color:grey"
        },
        {
          id: 3,
          nome: "LICENÇAS",
          icon: "colorize",
          iconStyle: "",
          style: "color:grey"
        },
        {
          id: 4,
          nome: "MARCAS",
          icon: "copyright",
          iconStyle: "",
          style: "color:grey"
        },
        {
          id: 5,
          nome: "TÍTULOS DE PUBLICAÇÃO",
          icon: "copyright",
          iconStyle: "",
          style: "color:grey"
        },
        {
          id: 6,
          nome: "RECEITAS, FÓRMULAS E PROJETOS",
          icon: "copyright",
          iconStyle: "",
          style: "color:grey"
        }
      ]
    };
  },
  methods: {
    selecionarBem(bem) {
      if (this.bemSelecionado) {
        bem.style = "background:#6B8E23;color:#fff";
        bem.iconStyle = "white";
      } else {
        (bem.style = "color:grey"), (bem.iconStyle = "");
      }
      this.bemSelecionado = !this.bemSelecionado;
    }
  },
  $_veeValidate: {
    validator: "new"
  }
};
</script>

<style lang="stylus"></style>