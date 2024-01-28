<template>
    <header>
        <div class="navbar navbar-default">
            <div class="navbar-header">
                <h1><router-link :to="{name: 'iMain'}">
                {{ sitename }}
            </router-link></h1>
            </div>
            <div class="nav navbar-nav navbar-right cart">
                <button type="button" class="btn btn-success" v-if="cartItemCount" @click="showCheckout">
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart" viewBox="0 0 16 16">
                            <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 8A.5.5 0 0 1 13 12H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5M3.102 4l1.313 7h8.17l1.313-7zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4m7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4m-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2m7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2"></path>
                        </svg>
                            {{ cartItemCount }}
                    </button>
                    <button type="button" class="btn btn-outline-secondary" disabled v-else>
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cart" viewBox="0 0 16 16">
                            <path d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 8A.5.5 0 0 1 13 12H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5M3.102 4l1.313 7h8.17l1.313-7zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4m7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4m-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2m7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2"></path>
                        </svg>
                            {{ cartItemCount }}
                    </button>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: 'my-header',
    data(){
        return{
            sitename: "Vue.js Pet Depot"
        }
    },
    props:['cartItemCount'],
    methods: {
        showCheckout(){
            this.$router.push({name: 'Form'});
        }
    }
}
</script>

<style scoped>
a {
    text-decoration: none;
    color: black;
}
</style>