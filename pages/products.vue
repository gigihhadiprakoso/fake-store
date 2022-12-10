<template>
    <Table :columns="fields" :rows="products" :action="action" :is-iterate-number="true" :is-pagination="true" :per-page="limit" :total-items="total_data" :current-page="1"/>
</template>

<script>
import SidebarMenu from "@/components/general/SidebarMenu.vue";
import Navbar from "@/components/general/Navbar.vue";
import Table from "@/components/general/Table.vue";

export default {
    components:{
        Navbar, SidebarMenu, Table
    },
    layout: 'custom',
    data(){
        return {
            fields: ['title', 'price', 'category'],
            products:[],
            action:['detail','edit','delete'],
            limit: 10,
            total_data: 0
        }
    },
    methods:{
        async getCount(){
            var count = await this.$axios.get('/products')
                .then( res  => {return res.data.length})
            
            return count
        },
    },
    async mounted(){
        this.total_data = await this.$axios.get('/products')
            .then( res => {return res.data.length})

        var url = '/products'
        url += '?limit='+this.limit;
        this.products = await this.$axios.get(url)
            .then(res => { return res.data})
    }
}
</script>