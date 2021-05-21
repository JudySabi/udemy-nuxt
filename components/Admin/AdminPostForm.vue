<template>
  <!-- le @submit est en lien direct avec le type="submit" de l'AppButton (donc la validation du form) -->
  <form @submit.prevent="onSave">
    <AppControlInput v-model="editedPost.author">Author Name</AppControlInput>

    <AppControlInput v-model="editedPost.title">Title</AppControlInput>

    <AppControlInput v-model="editedPost.thumbnailLink"
      >Thumbnail Link</AppControlInput
    >

    <AppControlInput control-type="textarea" v-model="editedPost.content"
      >Content</AppControlInput
    >
    <AppButton
      type="button"
      style="margin-left: 10px"
      btn-style="cancel"
      @click="onCancel"
      >Cancel</AppButton
    >
    <AppButton type="submit">Save</AppButton>
  </form>
</template>

<script>
import AppControlInput from "@/components/UI/AppControlInput";
import AppButton from "@/components/UI/AppButton";
export default {
  data() {
    return {
      editedPost: this.post
        ? {
            ...this.post // '...' est un spread operator, il permet de décomposer un objet
            // on ne passe pas l’objet en faisant ça, on passe une référence de cet objet à ta nouvelle variable
          }
        : {
            author: "",
            title: "",
            thumbnailLink: "",
            content: ""
          }
    };
  },
  methods: {
    onSave() {
      console.log(this.editedPost); // retourne un object avec toutes les valeurs attendues du formulaire
    },
    onCancel() {
      this.$router.push("/admin");
    }
  },
  components: {
    AppControlInput,
    AppButton
  },
  props: {
    post: {
      type: Object,
      required: false
    }
  }
};
</script>
