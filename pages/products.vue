<template>
    <div class="grid grid-cols-9">
        <div class="col-start-3 col-span-7 gap-2">
            <!-- <div v-for="product in products" :key="product.id">
                <Card :img="product.image" :title="product.title" :price="product.price" />
            </div> -->
            <Table :columns="fields" :rows="products" :action="action"/>
        </div>
    </div>
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
            fields: ['id', 'title', 'price', 'category'],
            products:[],
            action:['detail','edit','delete']
        }
    },

    mounted(){
        this.$axios.get('/products')
            .then(res => {
                this.products = res.data
            })
            .catch(err => {
                console.log(err.response.data)
            })
    }
}
</script>

<style>
body{
    background-color: #E3E3E3;
}
</style>