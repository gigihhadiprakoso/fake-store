<template>
    <nav aria-label="" v-if="perPage && total">
        <ul class="inline-flex items-center -space-x-px pl-6">
            <li v-for="count in totalPage" :key="count">
                <a href="#" 
                    class="
                        block
                        px-3 py-4 
                        leading-tight 
                        dark:bg-gray-800 
                        dark:border-gray-700 
                        dark:text-gray-400 
                        dark:hover:bg-gray-700 
                        dark:hover:text-white"
                    v-bind:class="getActivePage(count)"
                >
                    {{count}}
                </a>
            </li>
        </ul>
    </nav>
</template>
<script>
export default {
    name:'Pagination',
    props:['total', 'total-page', 'current-page', 'per-page'],
    methods:{
        getActivePage(page){
            return this.currentPage == page ? 
                "bg-primary-fakestore text-white" : 
                "text-gray-500 hover:bg-gray-100 hover:text-gray-700"
        }
    }
}
</script>