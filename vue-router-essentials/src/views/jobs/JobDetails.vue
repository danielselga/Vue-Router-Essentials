<template>
  <div v-if="job">
    <h1>{{job.title}}</h1>
    <p>The Job id is {{id}} </p>
    <!-- dentro do template não precisamos chamar o $route.params usando o this já na func data precisamos usar. -->
    <p>{{job.details}}</p>
  </div>
  <div v-else>
    <p>Loading job Details...</p>
  </div>
</template>

<script>
export default {
props: ['id'],

data(){
  return {
    job: null
  }
},
mounted(){
        //um lugar popular para dar fetch em dados.
         fetch('http://localhost:3000/jobs/' + this.id)
         .then((res) => res.json())
         .then(data => this.job = data)
         .catch(err => console.log(err.message))
    }
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