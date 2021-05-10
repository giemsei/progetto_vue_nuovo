<template>
  <h1>QUESTO È il test 2</h1>
  <cTest /> <!-- è equivalente a <cTest></cTest> -->
  <cTest msg="stringa" /> 
  <cTest msg2= "codice" :msg="testo" /> <!-- le proprietà che hanno i ":" davanti vedono l'oggetto dalla formula, quindi non va a riportare il valore del messaggio msg testo, ma la stringa assegnata in data -->
</template>

<script>
//richiamiamo il codice di test.js (passando per test2.vue dentro la cartella comp, cioè componenti) riutilizzando il codice senza problemi in test2.js
//usare i prefessi per indicare i componenti tipo "c" su cTest (per distinguere i componenti standard tipo h1,p,input ecc..)

import cTest from "@comp/test2.vue" //@comp che veine dalla configurazioni degli alias(file vite.config.js), non usare mai percorsi relativi o assoluti. 
export default {
    components: {
        cTest,
    },
    data(){
      return {
        testo: "stringa qualsiasi"
      }
    }

}
</script>

<style>

</style>