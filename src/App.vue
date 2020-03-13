<template>
  <div>  
    <ProductForm />
    <ProductItem descricao = descricao quantidade = quantidade valor = valor />
    <ProductsList produtos = produtos/>    
  </div>
</template>

<script>
import ProductItem from './components/ProductItem.vue'
import ProductsList from './components/ProductsList.vue'
import ProductForm from './components/ProductForm.vue'

export default {
  data() {
    return {
      isNameLimitExceeded: false,
      descricaoError: "",
      produtos: [
        {
          descricao: "",
          quantidade: 0,
          valor: 0,
        }
      ]
    };
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
