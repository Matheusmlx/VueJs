<template>
  <v-form>
    <div class="az-form-content">
      <v-container fluid class="grey lighten-5">
        <v-row justify="end">
          <v-col cols="1">
            <v-btn @click="novoDocumento" dark class="green text-white">Novo</v-btn>
          </v-col>
        </v-row>
        <!-- Componente-Documentos -->
        <v-row v-for="i in documentos" :key="i">
          <v-col cols="12">
            <v-row align="center" justify="center">
              <v-col cols="11">
                <v-card hover>
                  <v-row justify="center" class="ma-3 lighten-5">
                    <v-col cols="3">
                      <label>Número</label>
                      <v-text-field label="Digite o seu número" single-line outlined></v-text-field>
                    </v-col>
                    <v-col cols="3">
                      <label>Data</label>
                      <v-text-field
                        solo
                        label="__/__/___"
                        mask="###.###.###-##"
                        single-line
                        outlined
                        append-icon="calendar_today"
                      ></v-text-field>
                    </v-col>
                    <v-col cols="2">
                      <label>Valor</label>
                      <v-text-field solo label="R$ 0,00" single-line outlined></v-text-field>
                    </v-col>
                    <v-col cols="2">
                      <label>Tipo</label>
                      <v-select required :items="items" label="Selecione"></v-select>
                    </v-col>
                    <v-col cols="2">
                      <label>Anexo</label>
                      <v-text-field solo label="Selecione o Arquivo" single-line outlined></v-text-field>
                    </v-col>
                  </v-row>
                </v-card>
              </v-col>
              <v-col cols="1">
                <v-btn @click="removerDocumento(i)" icon class="grey">
                  <v-icon color="black">remove</v-icon>
                </v-btn>
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
      documentos: [{ id: 1 }],
      items: ["Item 1", "Item 2", "Item 3", "Item 4"]
    };
  },
  methods: {
    novoDocumento() {
      this.documentos.push({ id: this.documentos.length + 1 });
      console.log(this.documentos);
    },
    removerDocumento(documento) {
      this.documentos.splice(documento.id, 1);
    }
  },
  $_veeValidate: {
    validator: "new"
  }
};
</script>

<style lang="stylus"></style>