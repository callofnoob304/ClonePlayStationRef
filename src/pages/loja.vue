<template>
  <v-app>
    <v-app-bar height="200" flat>
      <v-row class="h-100">
        <v-col cols="12" md="12">
          <center>
            <v-img
            max-width="60"
            src="../../public/Imagens/icon-ps.png"
            ></v-img> 
            <span>PlayStation</span>
          </center>
        </v-col>
        <v-col cols="12" md="12" class="bg-grey-lighten-4 d-flex align-center">
          <v-row class="justify-space-between">
            <v-col md="11" class="ga-5 d-flex align-center">
              <span>PlayStation</span>
              <span>Jogos</span>
              <span>Hardware</span>
              <span>Serviços</span>
              <span>Notícias</span>
              <span>Loja</span>
              <span>Suporte</span>
            </v-col>
            <v-col md="1" class="text-center">
              <v-btn class="bg-primary"
              to="/loginPage"
              >Entrar</v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-app-bar>

    <v-main>
      <v-carousel v-model="currentImageIndex"
      class="h-screen" 
      :show-arrows="false" 
      cycle
      hide-delimiter-background
      delimiter-icon="mdi-minus">
        <v-carousel-item
        v-for="(image, index) in images" :key="index"
        :src="image"
        cover
        />
      </v-carousel>

      <v-row>
        <v-col v-for="(image, index) in images" :key="index"
        class="d-flex justify-center mt-10"
        >
          <v-hover  v-slot:default="{ props: hoverProps, isHovering}">
            <v-img
            v-bind="hoverProps"
            :class="['image-style', {'hover-effect' : isHovering }]"
            class="border-md border-opacity-100"
            :src="image"
            rounded="xl"
            max-width="50%"
            @click="currentImageIndex = index"
            ></v-img>
          </v-hover>
        </v-col>
      </v-row>

      <v-row class="h-screen align-center justify-center">
        <v-col md="5" class="text-center">
          <h1>Console de última geração</h1>
          <h3 class="mb-5 mt-5">Descubra uma nova geração de jogos incríveis <br> para a playstation.</h3>
          <v-btn class="bg-primary" >Acesse aqui!!</v-btn>
        </v-col>
        <v-col md="5">
          <v-img
          src="../../public/Imagens/playstation-5.webp"
          ></v-img>
        </v-col>
      </v-row>

      <v-row class="h-screen d-flex aling-center justify-center">
        <v-col v-for="i in products" :key="i.names"
        md="4" 
        class="d-flex flex-column justify-center align-self-center text-center"
        >
          <v-img
            :src="i.pictures"
            max-height="181"
          />
          <span class="mt-8 font-weight-medium text-h5"> 
            {{ i.names }} 
          </span>
        </v-col>
      </v-row>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent ({
  data() {
    return {
      images: [
        "../../public/Imagens/god-of-war.jpeg",
        "../../public/Imagens/halo.jpeg",
        "../../public/Imagens/TLOU.jpeg"
      ] as string[],
      products: [
        {
          pictures: "../../public/Imagens/playstation-5.webp",
          names: "PlayStation 5",
        },
        {
          pictures: "../../public/Imagens/controle-sem-fio.webp",
          names: "Controles sem fio",
        },
        {
          pictures: "../../public/Imagens/headset.webp",
          names: "Headset gamer",
        },
        {
          pictures: "../../public/Imagens/DualSense.webp",
          names: "DualSense Pro",
        },
        {
          pictures: "../../public/Imagens/Media-Remote.webp",
          names: "Controle remoto",
        },
        {
          pictures: "../../public/Imagens/hd-camera.webp",
          names: "Camera/Projetor Full HD",
        }
      ] as { names: string, pictures: string }[],
      currentImageIndex: 0 as number,
    }
  },

  mounted() {
    setTimeout(() => {
      alert("Seja bem vindo à loja!");
    }, 700 );
  },

  methods: {

  },
});
</script>

<style scoped>
  .v-row {
    margin: 0px !important;
  }

  .image-style {
    cursor: pointer;
    transition: all 0.5s ease-in-out;
    opacity: 0.7;
  }

  .hover-effect {
    transform: scale(1.05);
    opacity: 1;
  }
</style>