<template>
    <div>
     <input type="text" v-model="cari" placeholder="cari data">
     <ul>
        <li v-for="item in cariData" :key="item.id">
        {{ item.title }} - {{ item.price }}
        </li>
        <p v-if="cariData.length === 0">Hasil Tidak Ada</p>
     </ul>
    </div>
</template>

<script>
import { computed } from 'vue';

export default {
    data() {
        return {
            cari:'',
            products:[]
        };
    },
    created() {
            this.products = [
                {id: 1, title: "Baju Anak", price: 25000},
                {id: 2, title: "Susu Anak", price: 75000},
                {id: 3, title: "Topi", price: 10000},
                {id: 4, title: "Balon", price: 2000},
                {id: 5, title: "Kinder Joy KW", price: 1500}
            ]
       },
       computed: {
        cariData() {
            return this.products.filter((item) => {
                return item.title.match(this.cari);
            });
         }
       }
}
</script>