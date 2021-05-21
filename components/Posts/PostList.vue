<template>
  <section class="post-list">
    <!-- Vue comprend que :id-admin fait référence au isAdmin des déclaré dans les props et transforte le camelCase en snake-case -->
    <PostPreview
      id="1"
      :is-admin="isAdmin"
      thumbnail="https://c0.lestechnophiles.com/www.numerama.com/wp-content/uploads/2015/09/codesourcelignes.jpg?resize=1212,712"
      title="Programer Tools"
      previewText="Let's see the best tools for you"
    />
    <PostPreview
      id="2"
      :is-admin="isAdmin"
      thumbnail="https://photos.lci.fr/images/613/344/000_8wa6ct-9825da-0@1x.jpeg"
      title="Elon Musk"
      previewText="How become rich like him ?"
    />
  </section>
</template>

<script>
import PostPreview from "@/components/Posts/PostPreview";

export default {
  components: {
    PostPreview
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style scoped>
.post-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>
