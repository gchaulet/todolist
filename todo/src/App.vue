
<template>
  <div>
    <carousel>
      <carousel-slide v-for="n in slides" :key="n" :index="n - 1 ">
        <div style="position:absolute; left: 0; right: 0; text-align:center; top:50%; color: #FFF; font-size: 16px;">
          Slide {{ n }}
        </div>
        <img :src="'https://i.picsum.photos/id/' + n + '/900/400.jpg'" alt="image1" width="100%">
      </carousel-slide>
    </carousel>
    <button @click="addSlide">Add slide</button>
  </div>
</template>

<script>
import Todos from './components/Todos'
import Carousel from './components/Carousel/Carousel'
import CarouselSlide from './components/Carousel/CarouselSlide'

export default {
  data() {
    return {
      slides: 5,
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
    },
    addSlide() {
      this.slides++
    }
  },
  components: { 
    Todos,
    Carousel,
    CarouselSlide 
  }
}
</script>




