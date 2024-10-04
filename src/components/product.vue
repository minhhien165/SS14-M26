<template>
  <v-container>
    <v-row>
      <!-- Product Image Section -->
      <v-col cols="12" md="6">
        <v-carousel hide-delimiters>
          <v-carousel-item v-for="(image, index) in images" :key="index">
            <v-img :src="image" class="carousel-image"></v-img>
          </v-carousel-item>
        </v-carousel>

        <!-- Thumbnails -->
        <v-row class="mt-2">
          <v-col v-for="(image, index) in images" :key="index" cols="2">
            <v-img :src="image" class="thumb-image"></v-img>
          </v-col>
        </v-row>
      </v-col>

      <!-- Product Details Section -->
      <v-col cols="12" md="6">
        <div class="d-flex justify-space-between align-center mb-2">
          <v-chip color="green" text-color="white">In Stock</v-chip>
          <span>Kids</span>
        </div>

        <h2 class="product-title">Cute Soft Teddybear</h2>
        <p class="product-description">
          Vuhogi tulofi rutzihu zevowapz pi kanim wibrunci vebboji pomidwi gik
          zigzu ef fes arsce.
        </p>

        <div class="price-section mb-2">
          <span class="old-price">$175</span>
          <span class="new-price">$200</span>
        </div>

        <!-- Ratings -->
        <v-rating
          value="5"
          color="yellow"
          dense
          readonly
          total-visible="5"
        ></v-rating>
        <span>(236 reviews)</span>

        <!-- Color Options -->
        <v-row class="color-options mt-2">
          <v-col cols="2" v-for="color in colors" :key="color">
            <v-btn
              :color="color"
              class="color-circle"
              elevation="2"
              small
            ></v-btn>
          </v-col>
        </v-row>

        <!-- Quantity Selector -->
        <v-row class="mt-4">
          <v-col cols="3">
            <v-text-field
              v-model="quantity"
              label="Quantity"
              type="number"
              min="1"
            ></v-text-field>
          </v-col>
        </v-row>

        <!-- Action Buttons -->
        <v-row class="mt-4">
          <v-btn color="orange" large>Buy Now</v-btn>
          <v-btn color="cyan" large class="ml-4">Add to Cart</v-btn>
        </v-row>

        <!-- Dispatch Info -->
        <p class="dispatch-info mt-2">Dispatched in 2-3 weeks</p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from "vue";

const images = ref([
  "https://file.hstatic.net/200000472237/file/chup-anh-quan-ao-dep-bang-dien-thoai_ed543464b2c248588df949f9618361f8_grande.jpg",
  "https://mabustudio.com/?attachment_id=3204",
  "https://images.pexels.com/photos/996329/pexels-photo-996329.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500",
  "https://i.pinimg.com/550x/6e/93/49/6e93491371cb9cd3260178e196d98ccd.jpg",
]);

const colors = ref(["#ff5252", "#ff4081", "#00bcd4", "#8bc34a"]);
const quantity = ref(1);
</script>

<style scoped>
.carousel-image {
  height: 300px;
  object-fit: cover;
}

.thumb-image {
  height: 50px;
  width: 100%;
  object-fit: cover;
}

.product-title {
  font-size: 24px;
  font-weight: bold;
}

.product-description {
  color: gray;
  margin: 10px 0;
}

.old-price {
  text-decoration: line-through;
  color: gray;
  margin-right: 10px;
}

.new-price {
  font-size: 20px;
  font-weight: bold;
}

.color-circle {
  border-radius: 50%;
  height: 30px;
  width: 30px;
}

.dispatch-info {
  color: gray;
  font-size: 14px;
}
</style>
