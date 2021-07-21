<template>
  <div>
      <h1>jobs</h1>
      <div v-for="job in jobs" :key="job.id">
          <router-link :to="{name: 'JobDetails', params: {id: job.id}}">
              <!-- aqui estamos setando para a pagina jobdetails e passando como parametro o id setado no objeto jobs -->
              <!-- esse parametro vai ser passado lá no componente jobDetails que vai plotar na tela até então -->
              <h2>{{job.title}}</h2>
          </router-link>
      </div>
  </div>
</template>

<script>
export default {
    data(){
        return {
            jobs: [
                {title: 'Ux Designer', id: 1, details: 'lorem'},
                {title: 'Web Developer', id: 2, details: 'lorem'},
                {title: 'Vue Developer', id: 3, details: 'lorem'},
            ]
        }
    }
}
</script>

<style>

</style>