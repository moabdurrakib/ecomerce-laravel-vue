<template>
    <div>
        <hr>
         <button class="btn btn-warning mx-5"
                v-on:click.prevent="addProductToCart()">
            Add To Cart
        </button>
    </div>
</template>

<script>
    export default {

        data(){
            return{

            }

        },
        props:['productId','userId'],
        methods:{

            //Checking if Under logged in
          async addProductToCart(){
               if(this.userId == 0) {
                   this.$toastr.e('you Need to login, To add this product in Cart');
                   return;
               }
               // if user logged in then add item to cart
               let response = await axios.post('/cart',{
                   'product_id': this.productId
               });
               console.log(response.data);
           }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
