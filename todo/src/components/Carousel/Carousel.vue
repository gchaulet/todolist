<template>
    <div clas="carousel">
        <slot></slot>
        <button class="carousel__nav carousel__previous" @click="prev"><i class="fas fa-arrow-left"></i> Previous</button>
        <button class="carousel__nav carousel__next" @click="next">Next <i class="fas fa-arrow-right"></i></button>
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
            slides: []

        }
    },
    mounted () {
        //catch the object's childrens 
        //console.log(this.$children)
        this.slides = this.$children
        //function which give an index for each slide
        this.slides.forEach((slide, i) => {
            slide.index = i
        })
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
            // come back to slide 0 at the end
            if(this.index >= this.slidesCount){
                this.index = 0
            }
        },
        prev () {
            this.index--
            //go to last slide
            if(this.index < this.slidesCount){
                this.index = this.slidesCount - 1
            }
        }
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
</style>
