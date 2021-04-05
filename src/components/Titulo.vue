<template>
  <h1>{{ titulo }}</h1>
</template>

<script>
export default {
    name:'Titulo',
    props: {
        titulo: String
    }
}
</script>

<style>
    h1{
        font-weight: 300;
    }
</style>