<template>
  <v-app>
    <NavBar />
    <v-main>
      <v-container>
        <!-- Carrossel Responsivo -->
        <v-row>
          <v-col cols="12">
            <v-carousel height="60vh" :continuous="true" cycle>
              <v-carousel-item 
                v-for="(item, i) in items" 
                :key="i" 
                :src="item.src"
                cover
              >
                <v-row class="fill-height" align="center" justify="center">
                  <v-col cols="12" sm="6" class="text-center pa-6">
                    <h2 class="text-h4 text-md-h3 text-white mb-4">{{ item.title }}</h2>
                    <p class="text-body-1 text-white mb-6">{{ item.text }}</p>
                    <v-btn class="mt-2" color="primary">Comprar</v-btn>
                  </v-col>
                </v-row>
              </v-carousel-item>
            </v-carousel>
          </v-col>
        </v-row>

        <!-- Produtos Populares -->
        <v-row>
          <v-col cols="12">
            <v-toolbar color="transparent" class="mb-6 mb-md-8">
              <v-toolbar-title>Produtos populares</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn icon="mdi mdi-chevron-left"></v-btn>
              <v-btn icon="mdi mdi-chevron-right"></v-btn>
            </v-toolbar>
            <Popular />
          </v-col>
        </v-row>

        <!-- Novidades -->
        <v-row>
          <v-col cols="12">
            <v-toolbar color="transparent" class="mb-6 mb-md-8">
              <v-toolbar-title>Novidades</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn icon="mdi mdi-chevron-left"></v-btn>
              <v-btn icon="mdi mdi-chevron-right"></v-btn>
            </v-toolbar>
            <Featured />
          </v-col>
        </v-row>

        <!-- Clientes -->
        <v-row>
          <v-col cols="12">
            <Client />
          </v-col>
        </v-row>

        <!-- Produtos Destaques -->
        <v-row class="mt-8 mt-md-12">
          <v-col cols="12" sm="6" md="4" v-for="(product, i) in products" :key="i">
            <v-card class="mx-auto my-4" max-width="374">
              <v-row>
                <v-col cols="12" sm="6">
                  <v-card-item class="pt-6">
                    <v-card-title class="text-center text-subtitle-1 font-weight-bold">
                      {{ product.title }}
                    </v-card-title>
                    <v-card-text class="text-center">
                      {{ product.description }}
                      <v-btn color="black" block class="mt-4" dark>Comprar</v-btn>
                    </v-card-text>
                  </v-card-item>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-img 
                    height="200" 
                    class="mx-auto"
                    :src="product.image"
                    contain
                  ></v-img>
                </v-col>
              </v-row>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

      <Footer class="mt-12" />
    </v-main>
  </v-app>
</template>

<script setup>
import NavBar from '@/components/NavBar.vue';
import Popular from '../components/Popular.vue';
import Featured from '../components/Featured.vue';
import Client from '../components/Client.vue';
import Footer from '@/components/Footer.vue';
</script>

<script>
export default {
  data() {
    return {
      items: [
        {
          src: "7.jpg",
          title: "Surface Studio",
          text: "Le lorem ipsum est, en imprimerie, une suite de mots sans signification utilisée à titre provisoire pour calibrer une mise en page, le texte définitif venant remplacer le faux-texte dès ",
        },
        {
          src: "1.jpg",
          title: "Surface Studio",
          text: "Le lorem ipsum est, en imprimerie, une suite de mots sans signification utilisée à titre provisoire pour calibrer une mise en page, le texte définitif venant remplacer le faux-texte dès ",
        },
        {
          src: "2.jpg",
          title: "Surface Studio",
          text: "Le lorem ipsum est, en imprimerie, une suite de mots sans signification utilisée à titre provisoire pour calibrer une mise en page, le texte définitif venant remplacer le faux-texte dès ",
        },
        {
          src: "3.jpg",
          title: "Surface Studio",
          text: "Le lorem ipsum est, en imprimerie, une suite de mots sans signification utilisée à titre provisoire pour calibrer une mise en page, le texte définitif venant remplacer le faux-texte dès ",
        },
        {
          src: "4.jpg",
          title: "Surface Studio",
          text: "Le lorem ipsum est, en imprimerie, une suite de mots sans signification utilisée à titre provisoire pour calibrer une mise en page, le texte définitif venant remplacer le faux-texte dès ",
        },
        {
          src: "5.jpg",
          title: "Surface Studio",
          text: "Le lorem ipsum est, en imprimerie, une suite de mots sans signification utilisée à titre provisoire pour calibrer une mise en page, le texte définitif venant remplacer le faux-texte dès ",
        },
      ],
      products: [
        {
          title: "Purificador de ar",
          description: "Small plates, salads & sandwiches",
          image: "/image/13.jpg"
        },
        {
          title: "Asus Rog GT51CH‑AE004T Pc",
          description: "Small plates, salads & sandwiches",
          image: "/image/14.jpg"
        },
        {
          title: "CM 10 S2 Kule Hoparlör",
          description: "Small plates, salads & sandwiches",
          image: "/image/15.jpg"
        }
      ]
    };
  },
};
</script>

<style scoped>
/* Estilos responsivos para telas menores */
@media (max-width: 600px) {
  .text-h4 {
    font-size: 1.5rem !important;
  }
  
  .text-body-1 {
    font-size: 0.875rem !important;
  }
  
  .v-carousel-item__content {
    padding: 16px;
  }
}
</style>
