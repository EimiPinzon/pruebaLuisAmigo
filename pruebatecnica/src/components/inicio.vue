<template>
  <section>
    <h2>carro</h2>
    <p>marca: {{brand}}</p>
    <p>modelo: {{modelo}}</p>
    <p>color: {{color[3]}}</p>
    <p>precio: {{precio}} $</p>
    <p>power: {{power}} cv</p>
    {{mensaje.title}} - {{mensaje.text}}
  </section>
</template>

<script>


export default {

      data(){
        return{
            brand: "audi",
            modelo: "a4",
            color: ["azul", "rojo", "verde", "lila"],
            precio: 38000,
            power: 180,
            mensaje: {
                title: "hola mundo",
                text: "adios",
            }
        };
    },
  
    setup(){
        const brand = "audi";
        const modelo = "a4";
        const color = ["azul", "rojo", "verde", "marron"];
        const precio = 45000;
        const power = 2400;
        const mensaje = {
            title: "estoy bien",
            text: "welcome",
        };

        return {brand, modelo, color, precio, power, mensaje};
    },
};
</script>

<style>

</style>