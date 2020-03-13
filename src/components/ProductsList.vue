<template>
    <div>
      <ul>
        <li v-for="produto in produtos" :key="produto.descricao">
          <ProductItem :produto="produto" /> 
        </li>
      </ul>
      Total: {{qtdTotal}}        
    </div>  
    
</template>

<script>
import ProductItem from './ProductItem'
export default {
    name: 'ProductList',
    props: {
        produtos: Array
    },
    components: {
        ProductItem
    },
    computed: {
        qtdTotal(){
            return this.produtos.length;
        }
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
