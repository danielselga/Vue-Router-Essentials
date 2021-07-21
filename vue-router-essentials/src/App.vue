<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link :to="{name: 'About'}">About</router-link> |
    <router-link :to="{name: 'Jobs'}">Jobs</router-link> 
    <!-- quando bindamos o :to podemos chamar o rota via name. -->
    <!-- A vantagem de se usar o router-link é que ele não dá refresh na pagina. -->
  </div>
    <!-- Navegação pragmatica -->
    <button @click="redirect">Redirect</button>
    <button @click="back">Go Back</button>
    <button @click="forward">Go Foward</button>
  <router-view/>
</template>

<script>
export default {
  methods:{
    redirect(){
      this.$router.push({
        name: 'Home'
      })
    },
    back(){
      this.$router.go(-1)
    },
    forward(){
      this.$router.go(1)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
/* esse estilo css é aplicado ao router-link que está ativo. */
</style>

// $route é usado para pegar informação da rota
// $router é usado para quando queremos fazer alguma coisa.