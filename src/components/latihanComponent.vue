<template>
    <div v-if="age > 18">
    <h1>SELAMAT DATANG {{ name }}!</h1>
    </div>
    <div v-else>
        <p>MAAF KAMU BELUM CUKUP UMUR!</p>
    </div>
    <button @click="greet">sapa</button>
</template>
<script>
export default {
    props: ['name' , 'age'],
    methods: {
        greet() {
        alert("Hallo" + this.name)
        }
    },
}
</script>