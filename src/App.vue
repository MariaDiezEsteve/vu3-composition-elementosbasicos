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

  <span v-show="seMuestra"> Lorem ipsum dolor sit amet.</span>
  <!-- Esto será display:block cuando seMuestra sea true, y será display:none cuando seMuestra sea false -->

  <h3>Fruit List</h3>
  <ul>
    <li v-for = "(fruta , index) in arrayFrutas" :key="index"> {{ index  }} - {{ fruta }}   </li>
  </ul>

  <h3>Information about fruits</h3>
  <ul>
    <li v-for="(fruit, index) in arrayFruits" :key="fruit.name">
      <span v-if="fruit.stock > 20">  {{ index }} - {{ fruit.name }} - {{ fruit.price }} - {{ fruit.description }}</span>
   
    </li>
  </ul>


  <h3>Information about one fruit</h3>
  <ul>
    <li v-for="value in objetoFruta" :key="value">
      {{ value }}
    </li>
  </ul>

  <button @click="handleClick">Click aquí</button>

</template>

<script setup>

const name = "Vue dinámico"
const styleColor = "color: blue"
const arrayColores = ["blue", "red", "peru"]
const activo = false;
const decision = null;
const seMuestra = true

const arrayFrutas = ["cherry", "peach", "banana", "pineapple", "strawberry"];

const arrayFruits = [
  {
    name: "Mango",
    price: "2€",
    description: "El mango se vende por unidad",
    stock: 0

  },
  {
    name: "Orange",
    price: "1.5€",
    description: "Orange se vende por kilos",
    stock: 40

  },
  {
    name: "Kiwi",
    price: "2.9€",
    description: "Kiwi se vende por kilos",
    stock: 60

  }
]

const objetoFruta = {
  id: 1,
  name: "grapes",
  price: "5€",
  description:"A mount of grapes"

};


const  handleClick = () => {
  console.log("Me diste click")
};
</script> 


<style>

</style>
