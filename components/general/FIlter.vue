<template>
    <div class="bg-white rounded-lg shadow-md dark:bg-gray-800 dark:border-gray-700">
        <h3 class="sr-only">Categories</h3>
        <ul role="list" class="px-2 py-3 font-medium text-gray-900">
            <li v-for="category in categories" :key="category">
                <!-- <a :href="category.href" class="block px-2 py-3">{{ category.name }}</a> -->
                <span>{{category}}</span>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:'Filter',
    data(){
        return{
            categories: []
        }
    },
    mounted(){
        this.$axios.get('/products/categories') 
            .then(res => {
                this.categories = res.data
                console.log(this.categories)
            })
    }
}
</script>