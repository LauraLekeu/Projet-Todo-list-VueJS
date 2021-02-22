<!-- TEMPLATE -->
<template>

  <div class="header-top">
    <p> {{ titre }} </p>
  </div>

</template>

<!-- SCRIPT -->
<script>
  export default {
    name: 'Header',
    data() {
      return {
        titre : 'La To-Do Liste en Vue.js',
      }
    }
  }
  
</script>

<!-- STYLE -->
<style scoped>
  
  .header-top {
    position: fixed;
    top: 0;
    height: 50px;
    background: #333;
    color: #F1F1F1;
    width: 100%;
    text-align: center;
    line-height: 50px;
    font-size: 25px;
  }
</style>