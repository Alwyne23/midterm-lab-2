<template>
<v-container fluid>
<v-card
    color="#BBDEFB">
     <v-container>
  <v-card-title> String Manipulator </v-card-title>

   <v-text-field label="Enter word" v-model="text"></v-text-field>

   <v-card-actions  >
   <v-btn @click="outcome" >
        Results
   </v-btn>
   </v-card-actions>
     
Vowels: {{ vowels }} <br>
                         Numbers: {{ num }} <br>
                         Consonants: {{ cons }} <br>
                         Modified: {{ conv }} <br>
     </v-container>

 </v-card>  
</v-container>
 

</template>

<script setup>
import { ref } from 'vue'

const text = ref()
const vowels = ref(0)
const num = ref(0)
const cons = ref(0)
const conv = ref()

function outcome() {
     vowels.value = text.value.match(/[aeiou]/gi).length; // match to AEIOU
     num.value = text.value.match(/\d/g)?.length || 0; //match to digits otherwise 0
     cons.value = text.value.match(/[bcdfghjklmnpqrstvwxyz]/gi).length; //match to consonant
     conv.value = text.value.replace(/[aeiou]/gi, '*');
     return vowels.value, num.value, cons.value, conv.value
}


</script>
