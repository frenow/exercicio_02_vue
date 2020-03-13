<template>
  <div>
  
    <form @submit="onFormSubmit">
      <p>
        <label>Descrição do Produto:</label>
        <input type="text" v-model="descricao">
        {{descricaoError}}
      </p>
      <p>
        <label>Quantidade:</label>
        <input type="text" v-model="quantidade">
      </p>
      <p>
        <label>Valor:</label>
        <input type="text" v-model="valor">
      </p>
      <button type="submit">Send</button>
    </form>
    
 
  </div>
</template>

<script>

export default {

data() {
    return {
      descricao: "",
      quantidade: 0,
      valor: 0.00,
      isNameLimitExceeded: false,
      descricaoError: "",
      produtos: []
    };
  },
  watch: {
    descricao() {
      if (this.descricao.length > 15) {
        this.isNameLimitExceeded = true;
        this.descricaoError = "Descrição do produto não pode conter mais do que 15 caracteres";
      } else {
        this.isNameLimitExceeded = false;
        this.descricaoError = "";
      }
    }
  },
  methods: {
    onFormSubmit(e) {
      e.preventDefault();

      if (this.isNameLimitExceeded) {
        return;
      }

      this.produtos = this.produtos.concat({
        descricao: this.descricao,
        quantidade: this.quantidade,
        valor: this.valor
      });
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
