<template>
  <h1>QUESTO È IL COMPONENTE: {{msg}}</h1>
  <hr>
  <h2>questa è msg2 {{msg2}}</h2>
</template>

<script>
export default {
    data(){

    },
    methods: {

    },
    props: {
        msg:{
            type: String,
            default: ""
        },
        msg2: String 
    }
}
</script>

<style>

</style>