<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <div id="app">
      <header>
        <h1>Mi Perfil</h1>
      </header>
      <main>
        <ProfileHeader />
        <Skills />
        <Experience />
      </main>
    </div>
</template>

<script>
 import ProfileHeader from './components/ProfileHeader.vue';
  import Skills from './components/Skills.vue';
  import Experience from './components/Experience.vue';
  
  export default {
    components: {
      ProfileHeader,
      Skills,
      Experience,
    },
  };
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
</style>
