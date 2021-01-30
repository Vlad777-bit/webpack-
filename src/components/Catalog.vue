<template>
    <div class="catalog">
        <item 
            itemType="catalog" 
            v-for="item in items" 
            :item="item" 
            :key="item.id_product"
        />
    </div>
</template>

<script>
import item from './Item.vue'

export default {
    components: { item },
    data() {
        return {
            items: [],
            url: 'https://raw.githubusercontent.com/Vlad777-bit/static/master/JSON/JS2-JSON/catalog.json'
        }
    },
    mounted() {
        this.$parent.get(this.url).then(d => {
            this.items = d
        })
    }
}
</script>