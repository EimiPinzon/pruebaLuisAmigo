<template>
  <div>
    <table>
      <tbody>
        <tr>
          <td>celda</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from 'axios'

export default {
 data(){
   return{
     todos:null
     }
 },
 mounted(){
   console.log('hola mundooo')
   this.getTodos();
 },
 methods: {
   getTodos(){
     console.log('aca va el codigo de get todos.')
     axios
      .get('https://aws.random.cat/meow')
      .then(response =>{
          console.log(response)
          this.todos = response.data
      })
      .catch(e=> console.log(e))
   }
 }

 
}
</script>

<style>

</style>