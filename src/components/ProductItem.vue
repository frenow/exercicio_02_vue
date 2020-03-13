<template>
  <p>{{produto.descricao}} | {{produto.quantidade}} | {{produto.valor}}</p>
</template>

<script>
export default {
    name: 'ProductList',
    props: {
        produto: Object
    },
}
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
