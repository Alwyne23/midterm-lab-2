

<template>

<v-container fluid>
  <v-card color="#BBDEFB">
    
    <v-container>

    <v-text-field label="First Input" v-model.number="f_number"></v-text-field>
  <v-text-field label="Second Input" v-model.number="s_number"></v-text-field>

  <v-btn @click="doCompute">Result</v-btn>
  <br>
  Sum: {{ sum }} <br>
          Difference: {{ diff }} <br>
          Product: {{ prod }} <br>
          Quotient: {{ quo }} <br>
          Average: {{ ave }} <br>
          </v-container>
  </v-card>
  

</v-container>
 </template>

<script setup>
import {ref} from 'vue'
  const f_number = ref()
const s_number = ref()
const sum = ref(0)
const diff = ref(0)
const prod = ref(0)
const quo = ref(0)
const ave = ref(0)

function doCompute() {
  sum.value = f_number.value + s_number.value
  diff.value = f_number.value - s_number.value
  prod.value = f_number.value * s_number.value
  quo.value = f_number.value / s_number.value
  ave.value = (f_number.value + s_number.value) / 2
  return sum.value, diff.value, prod.value, quo.value, ave.value
}
</script>


