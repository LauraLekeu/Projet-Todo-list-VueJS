<!-- TEMPLATE -->
<template>

  <div class="container mt-5">
    <h1>Tâches à faire</h1>
    <hr />
    
    <form>
      <div class="form-group">
        <label for="action">Ajouter une tache:</label>
        <input type="text" name="" id="action" class="form-control">
      </div>
      <button class="btn btn-primary">Créer une tâche</button>
    </form>

    <ul class="mt-5">
      <li v-bind:key="index" v-for="(tache, index) in tableauTaches">
        <Item :tache="tache" :suppression="suppression"></Item>
      </li>
    </ul>
  </div>

</template>

<!-- SCRIPT -->
<script>
  import Item from './Item'

  export default {
    name: 'Contenu',
    data() {
      return {
        formData: {
          tache: ''
        },
        tableauTaches: ['Tâche 1', 'Tâche 2', 'Tâche 3']
      }
    },
    components: {
      Item
    }
  }
</script>
 
<!-- STYLE -->
<style>
  h1 {
    margin-top: 100px!important;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }
</style>
