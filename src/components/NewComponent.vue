<template>
    <MyComponents nama="fauzi" umur="17" ></MyComponents>
    <Footer sms="ini footer"></Footer>
    <latihanComponent name="fauzi" age="20" ></latihanComponent>
    <latihanDuaComponent></latihanDuaComponent>
    <watchersComponent nama="muhammad" umur="20" ></watchersComponent>
    <h2>Event Component</h2>
    
    
    
</template>


<script setup>

import MyComponents from './MyComponents.vue';
import Footer from './Footer.vue';
import latihanComponent from './latihanComponent.vue';
import latihanDuaComponent from './latihanDuaComponent.vue';
import watchersComponent from './watchersComponent.vue';


//event
import {ref} from 'vue';
const nama = ref('fauzi');
const umur = ref(25);

const onGreeted = () => {
    console.log('kamu udah disapa bro!');
};



</script>

