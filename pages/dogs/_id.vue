<template>
  <h1>dogs with id : {{ $route.params.id }}</h1>
</template>

<script>
export default {
  validate(data) {
    console.log(data); // retourne un objet avec les params query store etc...
    // return data.params.id == 1; // ne valide que si l'id est égal à 1
    return /^\d+$/.test(data.params.id); // regex qui permet de valider que les types number
  }
};
</script>
