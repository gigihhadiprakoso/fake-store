<template>
    <Table :columns="fields" :rows="products" :action="action" :is-iterate-number="true" :is-pagination="true" />
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
            action:['detail','edit','delete']
        }
    },

    mounted(){
        var url = '/products'
        var per_page = 10;

        if(per_page)
            url += '?limit='+per_page;

        this.$axios.get(url)
            .then(res => {
                this.products = res.data
            })
            .catch(err => {
                console.log(err.response.data)
            })
    }
}
</script>