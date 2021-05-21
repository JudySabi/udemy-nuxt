<template>
  <div>
    <v-text-field type="text" v-model="userId" />
    <v-btn @click="onLoadUser">Load user</v-btn>
    <!-- nuxt-child permet de récupérer l'enfant nommé de manière IDENTIQUE que le dossier en question. Pour l 'instant c'est donc users/index.vue si nous cliquons sur le btn onLoadUser, le text du bas changera et deviendra alors users/_id/index.vue -->
    <nuxt-child />
  </div>
</template>

<script>
export default {
  data() {
    return {
      userId: ""
    };
  },
  methods: {
    onLoadUser() {
      // push la view suivante :
      this.$router.push("/users/" + this.userId);
    }
  },
  layout: "users"
};
</script>

<style scoped>
input {
  background-color: darkslategray;
  border-radius: 3px;
}
</style>
