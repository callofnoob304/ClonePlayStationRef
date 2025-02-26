<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" temporary class="d-md-none">
      <v-list>
        <v-list-item
          v-for="(item, index) in navItems"
          :key="index"
          @click="drawer = false"
        >
          <v-list-item-title>{{ item }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar height="200" flat>
      <v-row class="h-100">
        <v-col cols="12">
          <center>
            <v-img max-width="60" src="/icon-ps.png"></v-img>
            <span>PlayStation</span>
          </center>
        </v-col>
        <v-col cols="12" md="12" class="bg-grey-lighten-4 d-flex align-center">
          <v-row class="justify-space-between" width="100%">
            <v-app-bar-nav-icon class="d-md-none" @click="drawer = !drawer" />
            <v-col class="d-none d-md-flex ga-5 align-center">
              <span v-for="(item, index) in navItems" :key="index" class="mx-2">
                {{ item }}
              </span>
            </v-col>
            <v-col cols="auto">
              <v-btn class="bg-primary" to="/loginPage">Entrar</v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-app-bar>

    <v-main>
      <!-- Carrosel -->
      <v-carousel
        v-model="currentImageIndex"
        class="h-auto"
        show-arrows="hover"
        cycle
        hide-delimiter-background
        delimiter-icon="mdi-minus"
      >
        <v-carousel-item
          v-for="(image, index) in images"
          :key="index"
          :src="image"
          cover
        />
      </v-carousel>

      <!-- Alternantes do carrosel -->
      <v-row class="justify-center">
        <v-col
          v-for="(image, index) in images"
          :key="index"
          cols="12"
          sm="6"
          md="4"
          lg="4"
          class="d-flex justify-center mt-5"
        >
          <v-hover v-slot:default="{ props: hoverProps, isHovering }">
            <v-img
              v-bind="hoverProps"
              :class="['image-style', { 'hover-effect': isHovering }]"
              class="border-md border-opacity-100"
              :src="image"
              rounded="xl"
              max-width="50%"
              @click="currentImageIndex = index"
            ></v-img>
          </v-hover>
        </v-col>
      </v-row>

      <!-- PlayStaion 5 -->
      <v-row class="align-center justify-center">
        <v-col cols="12" sm="12" md="5" lg="5" class="text-center">
          <h1>Console de última geração</h1>
          <h3 class="mb-5 mt-5">
            Descubra uma nova geração de jogos incríveis <br />
            para a playstation.
          </h3>
          <v-btn class="bg-primary">Acesse aqui!!</v-btn>
        </v-col>
        <v-col cols="12" sm="4" md="5" lg="4">
          <v-img src="/playstation-5.webp"></v-img>
        </v-col>
      </v-row>

      <!-- Produtos -->
      <v-row class="d-flex aling-center justify-center mb-10">
        <v-col
          v-for="i in products"
          :key="i.names"
          cols="12"
          sm="6"
          md="4"
          lg="4"
          class="d-flex flex-column justify-center align-self-center text-center"
        >
          <v-img :src="i.pictures" max-height="181" />
          <span class="py-10 font-weight-medium text-h5">{{ i.names }}</span>
        </v-col>
      </v-row>

      <!-- PlayStationPlus -->
      <v-row class="justify-space-evenly bg-gradient py-10">
        <v-col cols="12" md="5" class="d-flex justify-center">
          <v-img src="/PsPlus.webp" max-height="500" />
        </v-col>
        <v-col cols="12" md="5" class="align-self-center text-center">
          <h1 class="font-weight-regular mb-10 text-break">
            Melhore sua experiência PlayStation com o modo multijogador online,
            jogos mensais, descontos exclusivos e muito mais.
          </h1>
          <v-btn class="bg-primary w-auto mx-auto" size="x-large"
            >Explore o play plus!</v-btn
          >
        </v-col>
      </v-row>

      <!-- Footer -->
      <v-footer class="text-center align-start bg-black">
        <v-row>
          <v-col cols="12" sm="12" md="12" class="text-center">
            <v-btn icon="mdi-arrow-up" @click="scrollToTop" />
          </v-col>
          <v-col cols="12" sm="6" md="2">
            <h2>Sobre</h2>
            <h4>Sobre a SIE</h4>
            <h4>Carreiras</h4>
            <h4>Playstation Studio</h4>
            <h4>Empresarial</h4>
          </v-col>
          <v-col cols="12" sm="6" md="2">
            <h2>Produtos</h2>
            <h4>PS5</h4>
            <h4>PS4</h4>
            <h4>PS VR2</h4>
            <h4>PS Plus</h4>
            <h4>Acessórios</h4>
            <h4>Jogos</h4>
          </v-col>
          <v-col cols="12" sm="6" md="2">
            <h2>Valores</h2>
            <h4>Meio ambiente</h4>
            <h4>Acessibilidade</h4>
            <h4>Segurança online</h4>
            <h4>Diversidade, equidade e inclusão</h4>
          </v-col>
          <v-col cols="12" sm="6" md="2">
            <h2>Suporte</h2>
            <h4>Central de suporte</h4>
            <h4>Equipe de segurança do PlayStation</h4>
            <h4>Status da PSN</h4>
            <h4>Reparos do PlayStation</h4>
            <h4>Redefinição de senha</h4>
            <h4>Manuais</h4>
          </v-col>
          <v-col cols="12" sm="6" md="2">
            <h2>Recursos</h2>
            <h4>Termos de serviço da PSN</h4>
            <h4>Política e privacidade da PS Store</h4>
            <h4>Classificações etárias</h4>
            <h4>Alerta de saúde</h4>
            <h4>Desenvolvedores</h4>
          </v-col>
          <v-col cols="12" sm="6" md="2">
            <h2>Conectar</h2>
            <h4>Aplicativo iOS</h4>
            <h4>Aplicativo Android</h4>
          </v-col>
        </v-row>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    return {
      images: ["./god-of-war.jpeg", "./halo.jpeg", "./TLOU.jpeg"] as string[],
      products: [
        {
          pictures: "./playstation-5.webp",
          names: "PlayStation 5",
        },
        {
          pictures: "./controle-sem-fio.webp",
          names: "Controles sem fio",
        },
        {
          pictures: "./headset.webp",
          names: "Headset gamer",
        },
        {
          pictures: "./DualSense.webp",
          names: "DualSense Pro",
        },
        {
          pictures: "./Media-Remote.webp",
          names: "Controle remoto",
        },
        {
          pictures: "./hd-camera.webp",
          names: "Camera/Projetor Full HD",
        },
      ] as { names: string; pictures: string }[],
      currentImageIndex: 0 as number,
      drawer: false,
      navItems: [
        "PlayStation",
        "Jogos",
        "Hardware",
        "Serviços",
        "Notícias",
        "Loja",
        "Suporte",
      ] as string[],
    };
  },

  mounted() {
    setTimeout(() => {
      alert("Seja bem vindo à loja!");
    }, 700);
  },

  methods: {
    scrollToTop(): void {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
  },
});
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Quicksand:wght@300..700&display=swap");
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

.bg-gradient {
  background: linear-gradient(
    to top right,
    rgba(193, 193, 193, 1) 48%,
    rgba(248, 255, 0, 1) 100%
  );
}

.v-footer h4 {
  text-decoration: underline #fff;
  font-family: "Quicksand", serif;
  font-optical-sizing: auto;
  font-weight: 400;
  font-style: normal;
}

@media (max-width: 600px) {
  h1 {
    font-size: 1.8rem;
  }

  h3 {
    font-size: 1.2rem;
  }
}
</style>