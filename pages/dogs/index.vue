<template>
  <div>
    <v-text-field v-model="dogId" label="Id's Dog" outlined />
    <v-btn @click="onLoadDog">Load Dog</v-btn>
  </div>
</template>
<script>
export default {
  data() {
    return {
      dogId: ""
    };
  },
  methods: {
    onLoadDog() {
      this.$router.push("/dogs/" + this.dogId);
    }
  }
};
</script>
