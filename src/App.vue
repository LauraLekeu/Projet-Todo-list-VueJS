<!-- TEMPLATE -->
<template>

  <div id="app">
    <Header></Header>
    <Contenu></Contenu>
  </div>

</template>

<!-- SCRIPT -->
<script>
import Header from './components/Header.vue'
import Contenu from './components/Contenu.vue'

export default {
  name: 'App',
  components: {
    Header,
    Contenu
  }
}
</script>

<!-- STYLE -->
<style>
</style>
