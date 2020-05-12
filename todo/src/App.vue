<template>
  <div>
    {{ todos }}
    <todos v-model="todos"></todos>
    <todos></todos>
    <todos></todos>
    <button @click="addTodo">Ajouter</button>
  </div>
</template>

<script>
import Todos from './components/Todos'

export default {
  data() {
    return {
      todos: [{
        name: 'Demo',
        completed: true
      }]
    }
  },
  methods :{
    addTodo(){
      this.todos.push({
        name: 'Ejan',
        completed: false
      })
    }
  },
  components: { 
    Todos 
    }
}
</script>


