<!-- TEMPLATE -->
<template>

  <div class="container mt-5">
    <h1>Tâches à faire</h1>
    <hr />

    <form>
      <div class="form-group">
        <label for="action">Ajouter une tâche:</label>
        <input v-model="formData.tache" type="text" name="" id="action" class="form-control">
      </div>
      <button v-on:click.prevent="ajouterItem" class="btn btn-primary">Créer une tâche</button>
    </form>

    <ul class="mt-5">
      <li v-bind:key="index" v-for="(tache, index) in tableauTaches">
        <Item v-bind:id="index" :tache="tache" :supprimerItem="supprimerItem"></Item>
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
    mounted(){
      if(localStorage.getItem('tableauTaches')){
        try {
            this.tableauTaches = JSON.parse(localStorage.getItem('tableauTaches'));
          } catch(e) {
            localStorage.removeItem('tableauTaches');
          }
      } 
    },
    methods: {
      ajouterItem: function() {
        // S'assurer que l'utilisateur a entré quelque chose
        if (!this.formData.tache){
          return;
        }

        this.tableauTaches.push(this.formData.tache)
        this.formData.tache = ''
        this.saveTaches();
      },
      supprimerItem: function(e) {
        // console.log(e.target.parentNode.id)
        this.tableauTaches.splice(e.target.parentNode.id, 1) // l'index de l'élément à supprimer, le nombre d'éléments à supprimer
        this.saveTaches();
      },
      saveTaches() {
        const parsed =  JSON.stringify(this.tableauTaches)
        localStorage.setItem('tableauTaches', parsed)
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
