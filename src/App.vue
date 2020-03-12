<template>
  <div>
    <form @submit="onFormSubmit">
      <p>
        <label>First name:</label>
        <input type="text" v-model="firstName">
        {{firstNameError}}
      </p>
      <p>
        <label>Last name:</label>
        <input type="text" v-model="lastName">
      </p>
      <p>
        <label>E-mail:</label>
        <input type="text" v-model="email">
      </p>
      <button type="submit">Send</button>
    </form>
    <p>{{firstName}} {{lastName}} | {{email}}</p>

    <div>
      <ul>
        <li v-for="user in users" :key="user.name">{{user.name}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: "",
      lastName: "",
      email: "",
      firstNameError: "",
      users: []
    };
  },
  watch: {
    firstName() {
      if (this.firstName.length <= 5) {
        this.firstNameError = "Nome precisa conter mais do que 5 caracteres";
      } else {
        this.firstNameError = "";
      }
    }
  },
  methods: {
    onFormSubmit(e) {
      e.preventDefault();

      if (this.firstNameError !== "") {
        return;
      }

      this.users = this.users.concat({
        name: `${this.firstName}  ${this.lastName}`,
        email: this.email
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
