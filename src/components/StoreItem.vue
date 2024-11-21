<template>
  <v-card outlined class="ma-6">
    <v-row no-gutters>
      <!-- Product Info Section -->
      <v-col>
        <v-card-title>{{ product.data.name }}</v-card-title>
         <v-row>
          <v-col>
            <v-rating
              :model-value="product.data.rating" 
              color="amber"
              item-value="product.data.rating"
              max="5"
              :size="24"
              readonly
            >
            
            </v-rating>
            <v-chip color="green" text-color="white" label>Price: ${{ product.data.price }}</v-chip>
            <v-chip color="blue" text-color="white" label>Stock: {{ product.data.stock }}</v-chip>

          </v-col>
        </v-row>
        <v-img :src="product.data.image" :alt="product.data.name" height="200px"></v-img>
        
       

        <!-- Description -->
        <v-card-text>{{ product.data.description }}</v-card-text>

        <!-- Price and Stock -->
      
      </v-col>
    </v-row>
  </v-card>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";
import { ProductDoc } from "../types/product";

// Define the product prop
defineProps({
  product: {
    type: Object as () => ProductDoc,
    required: true,
  },
});
</script>
