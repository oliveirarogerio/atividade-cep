<template>
  <v-app>
    <v-main>
      <v-card class="d-flex justify-center pa-2" outlined tile>
        <div>
          <v-text-field
            label="Digite um CEP"
            hide-details="auto"
            v-model="input"
          ></v-text-field>

          <v-btn
            elevation="2"
            class="ma-2"
            outlined
            color="indigo"
            @click="buscaApi"
          >
            <v-icon left dark>
              mdi-magnify
            </v-icon>
            Pesquisar
          </v-btn>
        </div>
      </v-card>
      <div v-if="flagShow">
        <cepComponent :cepData="cepData"></cepComponent>
      </div>
    </v-main>
  </v-app>
</template>

<script>
import api from "./api/service.js";
import cepComponent from "./components/cepComponent";

export default {
  name: "App",

  components: {
    cepComponent: cepComponent,
  },

  data: () => ({
    input: "",
    cepData: {},
    flagShow: false,
  }),

  methods: {
    buscaApi: function() {
      api.get(`${this.input}/json`).then((data) => {
        this.cepData = data.data;
        console.log(this.cepData);
        this.flagShow = true;
      });
    },
  },
};
</script>
