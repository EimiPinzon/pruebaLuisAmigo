<template>
  <section>
    
    <div class="container">
      <div class="row">

        <img  alt="logo" src="./assets/makeup.jpg">
        
        <div class="col-md-12"><br><br>

          <table class="table table-bordered">
            <thead>
              <tr style="background-color: #d1e7dd;">
                <th scope="col">ID PRODUCTO</th>
                <th scope="col">PRODUCTO</th>
                <th scope="col">TIPO</th>
                <th scope="col">ETIQUETA</th>
                <th scope="col">FECHA DE CREACIÓN</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="todo in todos" :key="todo.id">
                <th scope="row">{{ todo.id }}</th>
                <td>{{ todo.category }}</td>
                <td>{{ todo.product_type }}</td>
                <td>{{ todo.tag_list[0] }}</td>
                <td>{{ todo.created_at }}</td>
              </tr>
            </tbody>
          </table>

        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";

export default {
  
  data() {
    return {
      todos: null,
    };
  },
  mounted() {
    console.log("hola mundooo");
    this.getTodos();
  },
  methods: {
    getTodos() {
      console.log("aca va el codigo de get todos.");
      axios
        .get("http://makeup-api.herokuapp.com/api/v1/products.json")
        .then((response) => {
          console.log(response);
          this.todos = response.data;
        })
        .catch((e) => console.log(e));
    },
  },
  
}


</script>

<style lang="css">
</style>
