<template>

    <!-- Nav  -->
    <ul class="nav bg-dark py-2 fixed-top ">
        <li class="nav-item"><router-link class="nav-link text-white" to="/">Home</router-link></li>
        <li class="nav-item"><router-link class="nav-link text-white" to="/product">Product</router-link></li>
        <li class="nav-item"><router-link class="nav-link text-white" to="/cart"><i class="fas fa-shopping-cart"></i>
                <small class="badge badge-danger" style="font-size: 11px;">{{ cart.length }}</small>
        </router-link>
        </li>
    </ul>

</template>

<script>
export default {
    name: 'NavBar',
    data() {
        return {
            cart: this.$root.cart
            // cart:[],
        };
    },
    // created() {
    //   this.cart = this.$root.cart;
    // }
}
</script>
