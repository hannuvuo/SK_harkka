<template>
  <div>
    <form @submit.prevent="addTodo">
      <input type="text" v-model="title" name="title" placeholder="<<< Kirjoita tähän uusi lisättävä muistutus >>>>>>>>>>">
      <input type="submit" class="btn" value="Tallenna uusi muistutus">
    </form>
  </div>
</template>

<script>
// import uuid from 'uuid';
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo() {
      const newTodo = {
        title: this.title,
        completed: false
      }
      // Send up to parent
      this.$emit('add-todo', newTodo);
      this.title = '';
    }
  }
}
</script>

// Tyylit jotka käytössä ainoastaan muistuksen lisäyksessä
<style scoped>
  form {
    display: flex;    
  }
  input[type="text"] {    
    flex: 10;
    padding: 20px;
    text-align: center;
  }
  input[type="submit"] {
    flex: right;    
  }
  input[type="submit"]:hover {
    background: rgb(185, 135, 250); 
  }
</style>