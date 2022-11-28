<template>
    <aside class="hidden pt-16 w-64 text-white fixed inset-y-0 overflow-x-hidden overflow-y-auto sm:block bg-white" aria-label="Sidebar">
        <div class="overflow-y-auto py-4 px-3 bg-gray-50 dark:bg-gray-800">
            <ul class="space-y-2">
                <li>
                    <a href="#" class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                        <font-awesome-icon icon="fa-solid fa-chart-pie" class="w-6 h-6 text-gray-500"/><span class="ml-3">Dashboard</span>
                    </a>
                </li>
                <!-- <li>
                    <button type="button" class="flex items-center p-2 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700" aria-controls="dropdown-example" data-collapse-toggle="dropdown-example">
                        <svg aria-hidden="true" class="flex-shrink-0 w-6 h-6 text-gray-500 transition duration-75 group-hover:text-gray-900 dark:text-gray-400 dark:group-hover:text-white" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 2a4 4 0 00-4 4v1H5a1 1 0 00-.994.89l-1 9A1 1 0 004 18h12a1 1 0 00.994-1.11l-1-9A1 1 0 0015 7h-1V6a4 4 0 00-4-4zm2 5V6a2 2 0 10-4 0v1h4zm-6 3a1 1 0 112 0 1 1 0 01-2 0zm7-1a1 1 0 100 2 1 1 0 000-2z" clip-rule="evenodd"></path></svg>
                        <span class="flex-1 ml-3 text-left whitespace-nowrap" sidebar-toggle-item="">E-commerce</span>
                        <svg sidebar-toggle-item="" class="w-6 h-6" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
                    </button>
                    <ul id="dropdown-example" class="hidden py-2 space-y-2">
                        <li>
                            <a href="#" class="flex items-center p-2 pl-11 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700">Products</a>
                        </li>
                        <li>
                            <a href="#" class="flex items-center p-2 pl-11 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700">Billing</a>
                        </li>
                        <li>
                            <a href="#" class="flex items-center p-2 pl-11 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700">Invoice</a>
                        </li>
                    </ul>
                </li> -->
                <!-- <li>
                    <a href="#" class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                    <svg aria-hidden="true" class="flex-shrink-0 w-6 h-6 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M8.707 7.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l2-2a1 1 0 00-1.414-1.414L11 7.586V3a1 1 0 10-2 0v4.586l-.293-.293z"></path><path d="M3 5a2 2 0 012-2h1a1 1 0 010 2H5v7h2l1 2h4l1-2h2V5h-1a1 1 0 110-2h1a2 2 0 012 2v10a2 2 0 01-2 2H5a2 2 0 01-2-2V5z"></path></svg>
                    <span class="flex-1 ml-3 whitespace-nowrap">Products</span>
                    <span class="inline-flex justify-center items-center p-3 ml-3 w-3 h-3 text-sm font-medium text-blue-600 bg-blue-200 rounded-full dark:bg-blue-900 dark:text-blue-200">3</span>
                    </a>
                </li>
                <li>
                    <a href="#" class="flex items-center p-2 text-base font-normal text-gray-900 rounded-lg dark:text-white hover:bg-gray-100 dark:hover:bg-gray-700">
                    <svg aria-hidden="true" class="flex-shrink-0 w-6 h-6 text-gray-500 transition duration-75 dark:text-gray-400 group-hover:text-gray-900 dark:group-hover:text-white" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd"></path></svg>
                    <span class="flex-1 ml-3 whitespace-nowrap">Users</span>
                    </a>
                </li> -->
                <li>
                    <button id="main-dropdown" type="button" 
                        class="
                            dropdown-toggle 
                            flex 
                            items-center
                            p-2 
                            w-full 
                            text-base 
                            font-normal 
                            text-gray-900 
                            rounded-lg 
                            transition 
                            duration-75 
                            group 
                            hover:bg-gray-100 
                            dark:text-white dark:hover:bg-gray-700"
                        @click="handleExpandMenu('dropdown-products')" 
                    >
                        <font-awesome-icon icon="fa-solid fa-shopping-bag" class="w-6 h-6 text-gray-500" />
                        <span class="flex-1 ml-3 text-left whitespace-nowrap" sidebar-toggle-item>Products</span>
                        <span id="dropdown-products-caret"><font-awesome-icon icon="fa-solid fa-chevron-down" /></span>
                    </button>
                    <ul id="dropdown-products" class="hidden py-2 space-y-2 z-50" aria-labelledby="main-dropdown">
                        <li>
                            <a href="/products" 
                                class="flex items-center p-2 pl-11 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700"
                            >
                                List Products
                            </a>
                        </li>
                        <li>
                            <a href="#" class="flex items-center p-2 pl-11 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700">Add Product</a>
                        </li>
                    </ul>
                </li>
                <li>
                    <button id="main-dropdown" type="button" 
                        class="
                            dropdown-toggle 
                            flex 
                            items-center
                            p-2 
                            w-full 
                            text-base 
                            font-normal 
                            text-gray-900 
                            rounded-lg 
                            transition 
                            duration-75 
                            group 
                            hover:bg-gray-100 
                            dark:text-white dark:hover:bg-gray-700"
                        @click="handleExpandMenu('dropdown-categories')" 
                    >
                        <font-awesome-icon icon="fa-solid fa-bars" class="w-6 h-6 text-gray-500"/>
                        <span class="flex-1 ml-3 text-left whitespace-nowrap">Categories</span>
                        <span id="dropdown-categories-caret"><font-awesome-icon icon="fa-solid fa-chevron-down" /></span>
                    </button>
                    <ul id="dropdown-categories" class="hidden py-2 space-y-2 z-50" aria-labelledby="main-dropdown">
                        <li>
                            <a href="/categories" 
                                class="flex items-center p-2 pl-11 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700">
                                List Categories
                            </a>
                        </li>
                        <li>
                            <a href="/add-category" 
                                class="flex items-center p-2 pl-11 w-full text-base font-normal text-gray-900 rounded-lg transition duration-75 group hover:bg-gray-100 dark:text-white dark:hover:bg-gray-700"
                            >
                                Add Category
                            </a>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </aside>
</template>
<script>
export default {
    name:'SidebarMenu',
    data(){
        return{
            isHidden: true,
        }
    },
    methods:{
        handleExpandMenu(elem){
            var element= document.getElementById(elem);
            var caret = document.getElementById(elem+"-caret")

            if(element.classList.contains('hidden')){
                element.classList.remove('hidden')
            } else{
                element.classList.add('hidden')
            }
        },
    }
}
</script>