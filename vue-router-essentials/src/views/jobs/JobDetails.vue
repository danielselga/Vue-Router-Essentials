<template>
  <h1>Job Details Page</h1>
  <p>The Job Details id is {{id}} </p>
  <!-- dentro do template não precisamos chamar o $route.params usando o this já na func data precisamos usar. -->
</template>

<script>
export default {
props: ['id'],

// Aqui estamos usando o this para chamar o $route.params
//     data(){
//         return {
//             id: this.$route.params.id
//         }
//     }
 }

</script>

<style>

</style>