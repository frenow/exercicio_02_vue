<template>
  <div>  
    <ProductForm :addProduto="addProduto" />
    <ProductsList :produtos="produtos" />
  </div>
</template>

<script>
import ProductForm from './components/ProductForm.vue'
import ProductsList from './components/ProductsList.vue'

export default {
  data() {
    return {
      produtos: [
        {
          descricao: "Video Game PS4",
          quantidade: 1,
          valor: 2000,
        },
        {
          descricao: "Video Game Xbox One",
          quantidade: 1,
          valor: 1500,
        },
        {
          descricao: "Video Game Nintendo Switch",
          quantidade: 1,
          valor: 2500,
        },
      ]
    };
  },
  components: {
    ProductsList,
    ProductForm
  }, 
  methods: {
    addProduto(produto){
      this.produtos = this.produtos.concat({
        descricao: produto.descricao,
        quantidade: produto.quantidade,
        valor: produto.valor
      })
    }
  }  
};
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
