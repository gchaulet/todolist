
<template>
  <div>
    <carousel>
      <carousel-slide>
        <div style="position:absolute; left: 0; right: 0; text-align:center; top:50%; color: #FFF; font-size: 16px;">
          Salut les gens
        </div>
        <img src="https://i.picsum.photos/id/1011/600/600.jpg" alt="image1" width="100%">
      </carousel-slide>
      <carousel-slide>
        <div style="position:absolute; left: 0; right: 0; text-align:center; top:50%; color: #FFF; font-size: 16px;">
          Au revoir les gens
        </div>  
        <img src="https://i.picsum.photos/id/1011/600/600.jpg" alt="image1" width="100%">
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




