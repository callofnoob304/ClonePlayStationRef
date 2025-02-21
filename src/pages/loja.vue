<template>
  <v-app>
    <v-app-bar height="200">
      <v-row class="h-100">
        <v-col cols="12" md="12">
          <center>
            <v-img
            max-width="60"
            src="../../public/logo.png"
            ></v-img> 
            <span>PlayStation</span>
          </center>
        </v-col>
        <v-col cols="12" md="12" class="bg-grey-lighten-4 d-flex align-center">
          <v-row class="justify-space-between">
            <v-col md="6" class="ga-5 d-flex align-center">
              <span>PlayStation</span>
              <span>Jogos</span>
              <span>Hardware</span>
              <span>Serviços</span>
              <span>Notícias</span>
              <span>Loja</span>
              <span>Suporte</span>
            </v-col>
            <v-col md="3" class="d-flex align-center text-end">
              <v-text-field
              placeholder="Pesquisar"
              density="compact"
              variant="outlined"
              hide-details
              ></v-text-field>
              <v-btn class="bg-info mx-2" variant="outlined">Pesquisar</v-btn>
              <v-btn class="bg-primary">Login</v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-app-bar>

    <v-main>
    </v-main>
  </v-app>
</template>

<script lang="ts">
  export default {
    data() {
      return {
        
      }
    },

    methods: {
      
    },
  }
</script>

<style>
  .v-row {
    margin: 0px !important;
  }

  .v-text-field {
    width: 100px;
  }
</style>