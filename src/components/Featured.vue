<template>
   <v-row>
    <v-col 
      v-for="(feature, i) in featured" 
      :key="i" 
      cols="12" 
      sm="6" 
      md="4" 
      lg="3"
    >
      <v-card class="mx-auto my-4 pb-4" max-width="374">
        <v-img height="250" class="mx-4" :src="feature.img"></v-img>
        <v-card-item class="mt-n4">
          <v-card-title class="text-center">
            {{ feature.title }}
          </v-card-title>
        </v-card-item>
        <v-card-text>
          <div class="text-center">
            {{ feature.bio }}
          </div>
          <v-row align="center" class="mx-0 mt-4">
            <v-rating 
              :model-value="4.5" 
              color="amber" 
              density="compact" 
              half-increments 
              readonly 
              size="small"
            ></v-rating>
            <v-spacer></v-spacer>
            <div class="text-center ms-4">{{ feature.price }}</div>
          </v-row>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
 export default {
     data: () => ({
    featured: [
      {
        img: "image/5.png",
        title: "Smartv Insignia 32",
        price: "R$ 1500",
        bio: " Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.",
      },
      {
        img: "image/6.png",
        title: "Auricular Beats Pro",
        price: "R$ 850",
        bio: " Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.",
      },
      {
        img: "image/7.png",
        title: "PS4 Pro",
        price: "R$ 2.199",
        bio: " Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.",
      },
      {
        img: "image/8.png",
        title: "HP Deskjet Ink Advantage 3835",
        price: "R$ 800",
        bio: " Small plates, salads & sandwiches - an intimate setting with 12 indoor seats plus patio seating.",
      },
    ],
  }),
 }

</script>

<style></style>
