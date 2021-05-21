<template>
  <div>
    <v-text-field label="Product" outlined v-model="productId" />
    <v-btn @click="onLoadProduct">Load Product</v-btn>
  </div>
</template>

<script>
export default {
  data() {
    return { productId: "" };
  },
  methods: {
    onLoadProduct() {
      this.$router.push("/products/" + this.productId);
    }
  }
};
</script>
