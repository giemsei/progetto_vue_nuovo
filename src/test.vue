<!-- tag template in html-->
<template>
  <p>paragrafo di test, esempio richiamo data msg: {{ msg }}</p>
  <!-- il testo modificato fatto sul browser tramite input viene salvato e riutilizzato con il bottone tramite la funzione debug -->
  <input type="text" v-model="msg" />
  <!-- i due bottoni sono equivalenti, @ è equivalente a v-on: -->
  <button v-on:click="debug()">debug</button>
  <button @click="cambia()">cambia</button>
  <br />
  <br />
  <p>il numero è {{ count }}</p>
  <input type="number" v-model="count" />
  <!-- come scrivere del codice js all'interno dell html, con la logica dell'if -->
  <p v-if="count > 5">è maggiore di 5</p>
  <p v-else-if="count > 3">è maggiore di 3</p>
  <p v-else>è minore o uguale a 3</p>
  <br />
  <!-- codice js ottenuto da una proprietà computata messa all'interno dell html-->
  <p>{{ msgCount }}</p>
  <hr />
  <hr />
  <hr />
  <input type="number" v-model="count" />
  <button @click="push()">push</button>
  <pre>{{ totali }}</pre>
  <!-- mostra il codice in formato JSON-->
  <p>{{ totali }}</p>
  <!-- mostra il codice in formato default versione 1-->
  <p v-text="totali"></p>
  <!-- mostra il codice in formato default versione 2-->
  <p v-for="(k, key) in totali" :key="key">il numero è {{ k + "," + key }}</p>
  <!-- la sintassi deve essere rispettata del for, c'è bisogno della chiave key!!, che è il conttattore dell'elemento del vettore, cioè l'indice-->
  <p v-for="(k, i) in totali" :key="i">il numero è {{ k + "," + i }}</p>
  <!-- uguale al codice sopra, per mostrare meglio la sintassi -->
  <!-- MI DA ERRORE L"EDITOR ma il for funziona senza il key, EDITOR vecchio!!!!!! -->
  <!--<p v-for="k in totali">il numero è {{k}}</p> -->
</template>

<!-- tag script in js-->
<script>
//classe export default sempre uguale per tutte le classi di vue
export default {
  //struttura per rappresentare internamente i dati
  data() {
    return {
      msg: "ciao",
      count: 0,
      totali: [],
    };
  },
  methods: {
    debug() {
      console.log("this.msg", this.msg);
    },
    cambia() {
      this.msg = new Date();
    },
    push() {
      this.totali.push(this.count);
    },
  },
  computed: {
    msgCount() {
      if (this.count <= 3) return "è minore o uguale a 3";
      else return "è maggiore di 3";
    },
  },
};
</script>

<!-- tag style in css-->
<style>
</style>