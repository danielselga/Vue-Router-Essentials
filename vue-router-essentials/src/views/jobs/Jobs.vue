<template>
  <div>
      <h1>jobs</h1>
      
        <div v-if="jobs.length">
            <div v-for="job in jobs" :key="job.id">
            <router-link :to="{name: 'JobDetails', params: {id: job.id}}">
                <!-- aqui estamos setando para a pagina jobdetails e passando como parametro o id setado no objeto jobs -->
                <!-- esse parametro vai ser passado lá no componente jobDetails que vai plotar na tela até então -->
                <h2>{{job.title}}</h2>
            </router-link>
        </div>
        </div>
        <div v-else>
            <p>Loading jobs...</p>
        </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            jobs: []
        }
    },
    mounted(){
        //um lugar popular para dar fetch em dados.
         fetch('http://localhost:3000/jobs')
         .then((res) => res.json())
         .then(data => this.jobs = data)
         .catch(err => console.log(err.message))
    }
}
</script>

<style>

</style>