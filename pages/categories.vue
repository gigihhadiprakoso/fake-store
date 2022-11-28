<template>
    <Table :columns="fields" :rows="categories" :action="action" :is-iterate-number="true"/>
</template>
<script>
import Navbar from "@/components/general/Navbar.vue";
import Table from "@/components/general/Table.vue";

export default {
    components:{
        Navbar, Table
    },
    layout: 'custom',
    data(){
        return {
            fields: ['title'],
            categories:[],
            action:['detail','edit','delete']
        }
    },

    mounted(){
        this.$axios.get('/products/categories')
            .then(res => {
                for(const data of res.data){
                    var arr = [];
                    arr['title'] = data;
                    this.categories.push(arr);
                }
            })
            .catch(err => {
                console.log(err.response.data)
            })
    }
    
}
</script>