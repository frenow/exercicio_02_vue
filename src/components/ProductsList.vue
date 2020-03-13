<template>
    <div>
      <ul>
        <li v-for="produto in produtos" :key="produto.descricao">{{produto.descricao}} | {{produto.quantidade}} | {{produto.valor}}</li>
      </ul>
    </div>  
</template>

<script>
export default {
  name: 'ProdutcsList',
  props: {
      produtos: []
  }
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
