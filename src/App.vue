<template>
  <TheHeader v-if="showHeader" />

  <div v-show="showName">
    Nome: {{ firstName }}
    <br>
    Sobrenome: {{ lastName }}
  </div>

  <div v-if="acessLevel === 'admin'">Admin</div>
  <div v-else-if="acessLevel === 'mkt'">Mkt</div>
  <div v-else>User</div>

  <div>
    <div v-for="obj in todos" :key="obj.id" class="todos-item">
      {{ obj.title }}
    </div>
  </div>

  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App" />
</template>

<script>
import TheHeader from './components/TheHeader.vue'
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    TheHeader,
    HelloWorld
  },
  data() {
    return {
      showHeader: true,
      firstName: "Leandro",
      lastName: "Ferraz",
      showName: true,
      acessLevel: '',
      todos: [
        {
          userId: 1,
          id: 1,
          title: "Automação"
        },
        {
          userId: 1,
          id: 2,
          title: "Programação"
        },
        {
          userId: 1,
          id: 2,
          title: "Qualidade"
        }
      ]
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
  margin-top: 60px;
}
 
.todos-item {
  background-color: aqua;
}
</style>
