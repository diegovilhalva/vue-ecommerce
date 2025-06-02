<template>
  <v-app>
    <NavBar />
    <v-main>
      <v-container class="pa-0 pa-sm-3">
        <!-- Carrossel otimizado para responsividade -->
        <v-carousel hide-delimiters height="auto" :show-arrows="$vuetify.display.mdAndUp">
          <v-carousel-item v-for="(item,i) in items" :key="i" :src="item.src" cover>
            <div class="carousel-content d-flex flex-column justify-center align-center fill-height pa-4">
              <h2 class="text-white text-h4 text-sm-h3 text-center mb-2">{{ item.title }}</h2>
              <p class="text-white text-center mb-6 text-body-1 text-sm-h6 max-width-600">{{ item.text }}</p>
              <v-btn color="primary" size="large" class="mt-sm-4">Comprar</v-btn>
            </div>
          </v-carousel-item>
        </v-carousel>

        <!-- Seções de produtos com header responsivo -->
        <section-header title="Produtos populares" class="mt-10" />
        <Popular class="mt-4" />

        <section-header title="Novidades" class="mt-10" />
        <Featured class="mt-4" />

        <Client class="my-10" />

        <!-- Cards otimizados para responsividade -->
        <v-row class="my-10" justify="center">
          <v-col v-for="(card, i) in cards" :key="i" cols="12" sm="6" md="4" lg="3">
            <v-card class="h-100 d-flex flex-column" :color="card.color">
              <v-row no-gutters class="flex-column-reverse flex-sm-row flex-grow-1">
                <v-col cols="12" sm="6" class="d-flex flex-column pa-4">
                  <v-card-title class="text-center text-break">{{ card.title }}</v-card-title>
                  <v-card-text class="text-center flex-grow-1">
                    {{ card.description }}
                  </v-card-text>
                  <div class="text-center mt-auto">
                    <v-btn color="black">Comprar</v-btn>
                  </div>
                </v-col>
                <v-col cols="12" sm="6" class="d-flex align-center justify-center">
                  <v-img :src="card.image" height="250" contain />
                </v-col>
              </v-row>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
      <Footer />
    </v-main>
  </v-app>
</template>

<script setup>
import NavBar from '@/components/NavBar.vue';
import Popular from '../components/Popular.vue';
import Featured from '../components/Featured.vue';
import Client from '../components/Client.vue';
import Footer from '@/components/Footer.vue';
import { ref, computed } from 'vue';
import { useDisplay } from 'vuetify';

const { mdAndUp } = useDisplay();

const items = ref([
  {
    src: "7.jpg",
    title: "Surface Studio",
    text: "Le lorem ipsum est, en imprimerie, une suite de mots sans signification utilisée à titre provisoire pour calibrer une mise en page."
  },
  // ... outros items
]);

const cards = ref([
  {
    title: "Purificador de ar",
    description: "Small plates, salads & sandwiches",
    image: "/image/13.jpg",
    color: null
  },
  {
    title: "Asus Rog GT51CH‑AE004T Pc",
    description: "Small plates, salads & sandwiches",
    image: "/image/14.jpg",
    color: "red"
  },
  {
    title: "CM 10 S2 Kule Hoparlör",
    description: "Small plates, salads & sandwiches",
    image: "/image/15.jpg",
    color: null
  }
]);

// Componente reutilizável para headers
const SectionHeader = {
  props: ['title'],
  template: `
    <v-row align="center" class="mx-0 mt-10 mb-4">
      <v-col cols="auto">
        <h2 class="text-h5 text-sm-h4">{{ title }}</h2>
      </v-col>
      <v-spacer />
      <v-col cols="auto" v-if="mdAndUp">
        <v-btn icon="mdi mdi-chevron-left" variant="text" />
        <v-btn icon="mdi mdi-chevron-right" variant="text" />
      </v-col>
    </v-row>
  `,
  setup() {
    return { mdAndUp }
  }
};
</script>

<style scoped>
.carousel-content {
  background: rgba(0, 0, 0, 0.4);
  text-shadow: 1px 1px 3px rgba(0,0,0,0.8);
}

.max-width-600 {
  max-width: 600px;
}

@media (max-width: 600px) {
  .carousel-content {
    padding-top: 80px !important;
    padding-bottom: 80px !important;
  }
}
</style>
