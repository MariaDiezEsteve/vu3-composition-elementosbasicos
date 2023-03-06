<template>
  <h1>{{ name }}</h1>
  <h2 :style="styleColor"> Soy azul</h2>
  <h2>{{ arrayColores }}</h2>
  <!-- Esta parte nos ayuda a saber que es lo que hay dentro del array, ya que VUE nos devuelve el array literal como si fuera un texto. -->
  <h3 :style="`color: ${arrayColores[2]}`">Soy peru color</h3>
  <!-- Podemos incluir la interpolación de javascript en el atributo style -->
  <h5>{{ activo ? "Estoy activo" : "Estoy inactivo" }}</h5>
  <!-- Como mostrar diferentes estados de una misma variable -- IMPORTANTE , esto solo funcionaría si tiene un retorno inmadiato-->
  <!-- V-IF  se renderizará uno de los tres componentes dependiendo del estado de la variable. -->
  <p v-if="decision === true"> La decisión es verdadera</p>
  <p v-else-if="decision === false">La descisión es falsa</p>
  <p v-else>La decisión es indecisa</p>

</template>

<!-- <script setup>
const name = "Vue dinámico"
const styleColor = "color: blue"
const arrayColores = ["blue", "red", "peru"]
const activo = false;
const decision = null;

</script> -->

<script>
export default {

  setup(){
    const name = "Vue dinámico"
    const styleColor = "color: blue"
    const arrayColores = ["blue", "red", "peru"]
    const activo = false;
    const decision = null;
    
    return {
      name,
      styleColor,
      arrayColores,
      activo,
      decision
    }
  }
}


</script>

<style>

</style>
