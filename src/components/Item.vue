<!-- TEMPLATE -->
<template>

  <div class="card my-2 item-todo">
    <p>{{tache}}</p>
    <div class="btn-supr btn btn-danger">x</div>
  </div>
  
</template>

<!-- SCRIPT -->
<script>
  export default {
    name: 'Item',
    props: ['tache', 'supression']
  }
</script>

<!-- STYLE -->
<style scoped>
  .item-todo {
    position: relative;
    padding: 20px 60px 20px 30px;
    font-size: 20px;
    height: 80px;
  }
  .btn-supr {
    position: absolute;
    top: 20px;
    right: 10px;
  }
  .item-todo p {
    margin-bottom: 0!important;
  }
</style>