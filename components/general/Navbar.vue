<template>
	<div class="mb-24">
		<!-- <nav class="bg-white px-2 sm:px-4 py-2.5 dark:bg-gray-900 fixed inset-x-0 z-50 w-full top-0 left-0 border-b border-gray-200 dark:border-gray-600 shadow-lg"> -->
		<nav class="fixed top-0 z-50 inset-x-0 h-16 justify-between bg-white dark:bg-gray-900 px-2 sm:px-4 py-2.5">
			<div class="container flex flex-wrap justify-between items-center mx-auto">
				<a href="https://fakestoreapi.com/" class="flex items-center">
					<img
						src="https://fakestoreapi.com/icons/logo.png"
						class="mr-3 h-6 sm:h-9"
						alt="Flowbite Logo"
					/>
					<span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white">Fake Store</span>
				</a>
				<div class="flex md:order-2">
					<button type="button" 
						class="
							text-gray-500 
							font-medium 
							rounded-lg 
							text-base  
							px-5 py-2.5 
							text-center 
							mr-3 md:mr-0 
							dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
					>
						<span> Administrator </span>
						<span><font-awesome-icon icon="fa-solid fa-user-circle" class="w-6 h-6 text-gray-500"/></span>
					</button>
					<button data-collapse-toggle="navbar-sticky" type="button" 
						class="
							inline-flex 
							items-center 
							p-2 
							text-sm 
							text-gray-500 
							rounded-lg 
							md:hidden 
							hover:bg-gray-100 
							focus:outline-none focus:ring-2 focus:ring-gray-200 
							dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600" 
						aria-controls="navbar-sticky" 
						aria-expanded="false"
					>
						<span class="sr-only">Open main menu</span>
						<svg class="w-6 h-6" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
							<path fill-rule="evenodd"
								d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
								clip-rule="evenodd">
							</path>
						</svg>
					</button>
				</div>
				<div 
					class="
						hidden
						justify-between
						items-center
						w-full
						md:flex md:w-auto md:order-1"
					id="navbar-sticky"
				>
				</div>
			</div>
		</nav>
		<SidebarMenu />
	</div>
</template>
<script>
import SidebarMenu from "@/components/general/SidebarMenu.vue";

export default {
	components:{
		SidebarMenu
	},
	name:'Navbar',
	props: ['is-sidebar']
}
</script>