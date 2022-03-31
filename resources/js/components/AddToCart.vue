<template>
    <div>
        <hr>
        <button class="btn btn-warning mx-5" v-on:click.prevent="addProductToCart()">
            Add To Cart
        </button>
    </div>
</template>

<script>
    export default {

        data(){

        },
        props:['productId','userId'],
        methods:{
           addProductToCart(){
               if(this.userId == 0) {
                   this.$toastr.e('you Need to login, To add this product in Cart');
                   return;
               }
           }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
