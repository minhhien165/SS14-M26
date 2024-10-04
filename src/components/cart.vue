<template>
  <v-container>
    <!-- Tabs for navigation -->
    <v-card flat>
      <v-tabs v-model="tab" background-color="light-blue lighten-4" centered>
        <v-tab class="px-5">
          <v-icon left>mdi-cart</v-icon> Item Cart
          <small class="subtitle-1 ml-2">Product Summary</small>
        </v-tab>
        <v-tab class="px-5">
          <v-icon left>mdi-receipt</v-icon> Billing
          <small class="subtitle-1 ml-2">Billing Information</small>
        </v-tab>
        <v-tab class="px-5">
          <v-icon left>mdi-credit-card</v-icon> Payment
          <small class="subtitle-1 ml-2">Add & Update Card</small>
        </v-tab>
      </v-tabs>
    </v-card>

    <!-- Cart details -->
    <v-card flat class="mt-4">
      <v-card-title
        class="d-flex justify-space-between align-center font-weight-bold"
      >
        <span>Product</span>
        <span>Price</span>
        <span>Quantity</span>
        <span>Total</span>
      </v-card-title>

      <!-- Product Table -->
      <v-divider></v-divider>
      <v-row class="py-4 align-center">
        <v-col cols="2">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
            class="rounded-lg"
            height="100"
          ></v-img>
        </v-col>
        <v-col cols="4">
          <div class="font-weight-bold">Cute Soft Teddybear</div>
          <small class="grey--text">size: 8 | Color: Dark Red</small>
        </v-col>
        <v-col cols="2">
          <div class="font-weight-bold">$200</div>
          <small class="text--secondary"><s>$175</s></small>
        </v-col>
        <v-col cols="2" class="d-flex align-center">
          <v-btn icon @click="decrement" outlined small>
            <v-icon>mdi-minus</v-icon>
          </v-btn>
          <span class="mx-2">{{ quantity }}</span>
          <v-btn icon @click="increment" outlined small>
            <v-icon>mdi-plus</v-icon>
          </v-btn>
        </v-col>
        <v-col cols="2" class="font-weight-bold"> $200 </v-col>
      </v-row>

      <!-- Order Summary -->
      <v-divider></v-divider>
      <v-row>
        <v-col cols="6">
          <v-card outlined class="pa-4">
            <v-card-title class="font-weight-bold">Order Summary</v-card-title>
            <v-divider></v-divider>
            <v-card-text>
              <v-row>
                <v-col>Sub Total</v-col>
                <v-col class="text-right">$200</v-col>
              </v-row>
              <v-row>
                <v-col>Discount 5%</v-col>
                <v-col class="text-right">- $10</v-col>
              </v-row>
              <v-row>
                <v-col>Shipping Charges</v-col>
                <v-col class="text-right">-</v-col>
              </v-row>
              <v-divider></v-divider>
              <v-row class="font-weight-bold">
                <v-col>Total</v-col>
                <v-col class="text-right">$190</v-col>
              </v-row>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>

      <!-- Buttons -->
      <v-row class="mt-4">
        <v-col class="d-flex justify-start">
          <v-btn outlined color="orange lighten-2" large
            >Continue Shopping</v-btn
          >
        </v-col>
        <v-col class="d-flex justify-end">
          <v-btn color="orange lighten-2" large>CheckOut</v-btn>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

const tab = ref(0);
const quantity = ref(1);

const increment = () => {
  quantity.value++;
};

const decrement = () => {
  if (quantity.value > 1) quantity.value--;
};
</script>

<style scoped>
.v-tabs {
  border-bottom: 2px solid #e0e0e0;
}
.v-card {
  box-shadow: none;
  border: 1px solid #e0e0e0;
  border-radius: 12px;
}
.v-btn {
  border-radius: 50px;
}
.v-card-title {
  background-color: #f9f9f9;
}
</style>
