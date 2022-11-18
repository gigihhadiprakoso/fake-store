<template>
    <button type="button" 
        class="
            text-white
            bg-yellow-400 
            hover:bg-yellow-500 
            focus:ring-4 
            focus:outline-none 
            focus:ring-yellow-500 
            rounded-sm
            text-sm 
            p-1 
            mx-1
            text-center 
            inline-flex 
            items-center ">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 5H6a2 2 0 00-2 2v11a2 2 0 002 2h11a2 2 0 002-2v-5m-1.414-9.414a2 2 0 112.828 2.828L11.828 15H9v-2.828l8.586-8.586z"></path></svg>
    </button>
</template>
<script>
export default{
    name:'EditButton'
}
</script>