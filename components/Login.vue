<template>
    <div class="container flex h-screen">
        
        <div v-if="isLoading" class="overlay-loading"><p>Loading...</p></div>

        <div class="box-border border-2 py-1 px-5 shadow-lg md:w-1/5 w-full align-middle m-auto">
            <h1 class="">Log In</h1>
            <form>
                <div class="mb-4">
                    <label class="block font-bold" for="username">Username</label>
                    <input type="text" v-model="username" class="block px-3 py-2 w-full border rounded-md shadow-sm">
                </div>
                <div class="mb-4">
                    <label class="block font-bold" for="password">Password</label>
                    <input type="password" v-model="password" class="block px-3 py-2 w-full border rounded-md shadow-sm">
                </div>
                <div class="mb-4">
                    <button class="block w-full pink-500" type="submit" @click.stop.prevent="onSubmit()">Sign In</button>
                </div>
            </form>
        </div>
        <!-- <div class="w-full mb-2 md:w-1/2 md:mx-4 border rounded shadow-sm" v-for="product in products" :key="product.id">
            <div class="px-4 py-4">
                <div>
                    <a href="#" class="font-semibold leading-tight text-2xl text-gray-800 hover:text-gray-800"> {{product.title}}</a>
                </div>
                <hr class="border-gray-200 my-1 border-bottom-none" style="border-top-width:0">
                <p class="text-gray-900">
                    {{product.description}}
                </p>
                <div class='flex text-gray-700 text-sm '>
                    <div class="pr-3">{{product.category}}</div> 
                </div>
            </div>
        </div> -->
    </div>
    <!-- <section class="section">
        <div class="container">
            <div class="columns">
                <div class="column is-4 is-offset-4">
                    <h2 class="title has-text-centered">Login</h2>
                    <Notification :message="error" v-if="error"/>

                    <form method="post" @submit.prevent="register">
                        <div class="field">
                            <label class="label">Username</label>
                            <div class="control">
                                <input type="text" class="input" name="username" v-model="username" required />
                            </div>
                        </div>
                        <div class="field">
                            <label class="label">Password</label>
                            <div class="control">
                                <input type="password" class="input" name="password" v-model="password" required/>
                            </div>
                        </div>
                        <div class="control">
                            <button type="submit" class="button is-dark is-fullwidth">Login</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </section> -->
</template>

<script>
import axios from 'axios'
import Notification from '~/components/general/Notification'

export default {
    components:{
        Notification,
    },
    name:'Login',
    data(){
        return{
            username:"",
            password:"",
            isLoading:false,
            errorMsg:null,
        }
    },
    methods:{
        onSubmit(){
            this.isLoading = true;
            let data = {
                username: this.username,
                password: this.password
            };
            
            axios.post("https://fakestoreapi.com/auth/login", data)
            .then(response => {
                this.isLoading = false;
                if(response.data.token){
                    localStorage.setItem("tokenLogin", response.data.token)
                }
            })
            .catch(error => {
                this.isLoading = false;
                if(error.response.status){
                    this.errorMsg = error.response.data
                }
            })
        }
    }
}
</script>

<style scoped>
    .overlay-loading {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        text-align: center;
        padding-top: 200px;
        font-size: 30px;
        font-family: sans-serif;
    }
</style>