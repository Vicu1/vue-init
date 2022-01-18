<script>

export default {
  name: 'App',
  components: {

  },
  data: () =>({
    model: {
      name: "",
      email: "",
      password: ""
    },
    error: "",
  }),

  methods: {
    submit() {
      if(!Object.keys(this.model).every(key => this.model[key])){
        this.error = "Failed";
      }else{
        this.error = "Success";
      }
    }

  }
}

</script>

<template>
  <div id="app">
    <form @submit.prevent class="form">
      <input @keypress.space="submit()" v-model="model.name" type="text" placeholder="Name">
      <input v-model="model.email" type="email" placeholder="Email">
      <input v-model="model.password" type="password" placeholder="Password">
      <button @click="submit()" id="button" type="submit">
        Submit
      </button>
      <span>{{ error }}</span>
    </form>
  </div>
</template>



<style>
  .form{
    display: flex;
    flex-direction: column;
    width: 400px;
  }
  input{
    margin: 5px 0;
    padding: 7px;
  }
  button{
    width: 100px;
    padding: 10px 0;
  }
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
