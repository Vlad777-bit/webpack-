<template>
    <div>
        <header class="header">
            <div class="form">
                <input type="text" class="search" placeholder="Что искать?"> 
                <!-- <input type="submit" class="btn search_btn" value="Поиск"> -->
            </div>
            
            <button id="basketBtn" class="btn">Корзина</button>
        </header>
        <main class="container">
            <catalog @add="addItem" />

            <basket ref="basket"/> 
        </main> 
    </div>
</template>

<script>
import Catalog from '../components/Catalog.vue'
import Basket from '../components/Basket.vue'

export default {
    components: {
        'catalog': Catalog,
        'basket': Basket
    },
    data() {
        return {}
    },
    props: {},
    methods: {
        addItem(item) {
            this.$refs.basket.add(item)
        },
        get(url) {
            return fetch(url).then(data => data.json())
        }
    },
    mounted() {},
}
</script>

