<template>
    <div>
    <p >haiiiii</p>
    <h1>pppppp</h1>
       <p>Nama : {{ nama }}</p>
       <p>Umur : {{ umur }}</p>
    </div>
</template>

<script>
export default { 
    props: ['nama','umur'],
    data() {
        return {
            message: "Ini adalah pesan dari komponen"
        }
    },
    methods: {
        greet() {
            console.log("Haloo")
        }
    },
}
</script>

<style>
h1 {
    color: green;
}

p {
    size: 16px;
}
</style>