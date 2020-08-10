<template>
    <div>
        <pre>{{stocks}}</pre>
        <app-stock v-for="(stock, index) in stocks" :key="index" :stock="stock"></app-stock>
    </div>
</template>

<script>
import {mapGetters} from 'vuex'
import Stock from './Stock.vue'

export default {
    mounted() {
        console.log(mapGetters)
    },
    computed: {
        ...mapGetters({
            stocks: 'stockPortfolio'
        })
    },
    components: {
        appStock: Stock
    }
}
</script>