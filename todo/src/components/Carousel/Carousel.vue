<template>
    <div clas="carousel">
        <slot></slot>
        <button class="carousel__nav carousel__previous" @click.prevent="prev"><i class="fas fa-arrow-left"></i> Previous</button>
        <button class="carousel__nav carousel__next" @click.prevent="next">Next <i class="fas fa-arrow-right"></i></button>
        <div class="carousel__pagination">
            <button v-for="n in slidesCount" :key="n" @click="goto(n-1)" :class="{active: n-1 == index}"></button>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        //console.log(this.$children)
        return {
            //know the current index
            index: 0,
            //cannot catch the object's childrens because previous console.log(this.$children) is empty 
            slides: [],
            direction: 'right'

        }
    },
   
    computed : {
        //count total number of slides available
        slidesCount () {
            return this.slides.length
        }
    },
    methods : {
        next () {
            this.index++
            this.direction ='right'
            // come back to slide 0 at the end
            if(this.index >= this.slidesCount){
                this.index = 0
            }
        },
        prev () {
            this.index--
            this.direction='left'
            //go to last slide
            if(this.index < this.slidesCount){
                this.index = this.slidesCount - 1
            }
        },
        goto(index) {
            this.direction = index > this.index ? 'right' : 'left'
            this.index = index
        }
    },
     mounted () {
        //catch the object's childrens 
        //console.log(this.$children)
        this.slides = this.$children
        //function which give an index for each slide
        // this.slides.forEach((slide, i) => {
        //     slide.index = i
        // })
    }
}
</script>

<style>
    .carousel {
        position: relative;
    }

    .carousel__nav {
        position: relative;
    }

    .carousel__pagination {
        position: absolute;
        top: 620px;
        left: 0;
        right: 0;
        text-align: center;
    }

    .carousel__pagination button {
        display: inline-block;
        width: 10px;
        height: 10px;
        background-color: #000;
        opacity: 0.8;
        border-radius: 10px;
        margin: 0 2px;
    }

    .carousel__pagination button.active {
        background-color: #fff;
    }
</style>
