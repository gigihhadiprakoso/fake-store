<template>
    <div id="app">
        <Navbar />
        <Nuxt />
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