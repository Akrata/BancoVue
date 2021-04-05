<template>
  <button @click="accion" :disabled="desactivar">{{texto}}</button>
</template>

<script>
export default {
props: {
    texto: {
        type: String
    },
    desactivar:{
        type: Boolean,
        default: false,
    }
},
methods: {
    accion() {
        this.$emit('signal')
    }
},
}
</script>

<style>

</style>