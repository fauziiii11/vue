<script setup>
import { ref } from 'vue'

let msg = "MUHAMMAD"
let rawHtml = "<h1>FAUZI</h1>"
let link = "https://id.wikipedia.org/wiki/Pesta_Olahraga_Asia_Tenggara_2023"
let aa = 10
let bb = 5
let tambah = aa + bb
let kurang = aa - bb



</script>

<template>
  <div id ="app">
    <span>{{ msg }}</span> <br>
    <span v-html="rawHtml"></span> <br>
    <a v-bind:href="link">KLIK</a> <br>
    <p><button v-bind:disabled="isButtonDisabled" onclick="alert('disabled')">DISABLED</button></p> <br>
    <p v-if="seen">sekarang anda bisa melihatku</p>
    <a v-on:click="doSomething">HAI</a> <br>

    bilangan1 = {{ aa }} <br>
    bilangan2 = {{ bb }} <br>
    hasil penambahan = {{ tambah }} <br>
    hasil pengurangan = {{ kurang }}
    
    
    
    
    </div>
    </template>