<template>
  <v-card class="d-flex flex-column justify-center pa-2" outlined tile>
    <cepDataField atributo1="Bairro" :atributo2="cepData.bairro"></cepDataField>
    <cepDataField
      atributo1="Complemento"
      :atributo2="cepData.complemento"
    ></cepDataField>
    <cepDataField atributo1="DDD" :atributo2="cepData.ddd"></cepDataField>
    <cepDataField atributo1="GIA" :atributo2="cepData.gia"></cepDataField>
    <cepDataField atributo1="IBGE" :atributo2="cepData.ibge"></cepDataField>
    <cepDataField
      atributo1="Localidade"
      :atributo2="cepData.localidade"
    ></cepDataField>
    <cepDataField
      atributo1="Logradouro"
      :atributo2="cepData.logradouro"
    ></cepDataField>
    <cepDataField atributo1="SIAFI" :atributo2="cepData.siafi"></cepDataField>
    <cepDataField atributo1="UF" :atributo2="cepData.uf"></cepDataField>
  </v-card>
</template>

<script>
import cepDataField from "./cepDataField";
export default {
  components: {
    cepDataField: cepDataField,
  },
  props: ["cepData"],
};
</script>

<style></style>
