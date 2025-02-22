<template>
  <v-row class="h-screen">
    <v-col class="d-flex justify-center align-center">
      <v-card class="w-25  rounded-ts-xl rounded-be-xl" elevation="8">
        <v-card-title
        class="text-center"
        >
          <h2>{{ login == true ? "Login" : "Cadastro" }}</h2>
        </v-card-title>
        <v-card-text>
          <v-text-field
            v-model="nome"
            v-if="!login"
            class="mb-5"
            label="Nome"
            variant="outlined"
            hide-details
          ></v-text-field>
          <v-text-field
            v-model="email"
            label="E-mail"
            variant="outlined"
            hide-details
          ></v-text-field>
          <v-text-field
            v-model="senha"
            class="mb-5 mt-5"
            label="Senha"
            variant="outlined"
            hide-details
          ></v-text-field>
          <v-row class="justify-space-around">
            <v-btn
              class="bg-primary w-25"
              @click="controlaFormulario"
            >{{ login == true ? "Cadastro" : "Login" }}</v-btn>
            <v-btn
              class="bg-success w-25"
              @click="validaLogin"
            >{{ login == true ? "Entrar" : "Cadastrar" }}</v-btn>
          </v-row>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      login: true as boolean,
      nome: null as string | null,
      email: null as string | null,
      senha: null as string | null,
    };
  },

  methods: {
    validaLogin(): void {
      if (this.login) {
        if (this.email != 'teste@gmail.com' && this.senha != '1234') {
          alert("E-mail ou senha incorretos! Tente novamente.");
          this.email = null;
          this.senha = null;
          return;
        };

        this.$router.push({ name: 'loja' });
        return;
      };
      
      alert('Cadastrado com sucesso!');
      this.login = true;
      this.nome = null;
      this.email = null;
      this.senha = null;
    },

    controlaFormulario(): void {
      if (this.login == false) {
        this.login = true;
        return;
      };

      this.login = false;
    },
  },
});
</script>

<style scoped>
  .v-row {
    margin: 0px !important;
  }
</style>