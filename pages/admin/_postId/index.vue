<template>
  <div class="admin-post-page">
    <section class="update-form"><AdminPostForm :post="loadedPost" /></section>
  </div>
</template>

<script>
import AdminPostForm from "@/components/Admin/AdminPostForm";
import AppButton from "@/components/UI/AppButton";
export default {
  components: {
    AdminPostForm
  },
  data() {
    return {
      loadedPost: {
        author: "Julie",
        title: "Awesome post",
        content: "thanks for that",
        thumbnailLink:
          "https://c0.lestechnophiles.com/www.numerama.com/wp-content/uploads/2015/09/codesourcelignes.jpg?resize=1212,712"
      }
    };
  }
};
</script>
