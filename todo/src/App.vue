
<template>
  <div>
    <carousel>
      <carousel-slide>
        Salut les gens
        <img src="https://i.picsum.photos/id/1011/600/600.jpg" alt="image1">
      </carousel-slide>
       <carousel-slide>
        Au revoir les gens
        <img src="https://i.picsum.photos/id/1012/600/600.jpg" alt="image1">
      </carousel-slide>
    </carousel>
    <todos v-model="todos"></todos>
    
  </div>
</template>

<script>
import Todos from './components/Todos'
import Carousel from './components/Carousel/Carousel'
import CarouselSlide from './components/Carousel/CarouselSlide'

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
    Todos,
    Carousel,
    CarouselSlide 
    }
}
</script>




