<template>
    <div  v-show="visible">
          Index : {{ index }}
          Visible ? {{ visible }}
        <slot></slot>
    </div>
</template>


<script>
export default {
    data () {
        return {
            index : 0
        }
    },
    computed : {
        visible() {
            //this index must be equal to the current index of my carousel
            return this.index === this.$parent.index
        }
    }
}
</script>
