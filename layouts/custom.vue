<template>
    <div id="app">
        <Navbar />
        <div class="grid grid-cols-12 gap-x-36">
            <div class="col-start-3 col-span-9">
                <Nuxt />
            </div>
        </div>
    </div>
</template>
<script>
import Navbar from "@/components/general/Navbar.vue";

export default {
    name:'custom',
    components:{
        Navbar
    }
}
</script>
<style>
body{
    background-color: #E3E3E3;
}
</style>