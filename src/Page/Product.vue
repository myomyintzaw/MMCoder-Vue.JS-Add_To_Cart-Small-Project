<template>
    <Master>
        <!-- loader  -->
        <!-- <Loader v-if="isload" /> -->
        <loader v-show="isload" />

        <!-- Content -->
        <div v-show="!isload" class="container mt-5">
            <div class="row">
                <!-- <div v-for="product in products" :key="product.id" class="col-md-4"> -->
                <div v-for="(p, i) in products" :key="i" class="col-md-4">

                    <div class="card p-3 m-3">
                        <div class="card-header">
                            <h5>{{ p.title }}</h5>
                            <div class="card-body">
                                <!-- <img src="https://s.alicdn.com/@sc04/kf/HTB1RH1XavvsK1Rjy0Fiq6zwtXXap.jpg_480x480.jpg"
                                    class="img-fluid" alt=""> -->
                                <img :src="p.thumbnail" class="img-fluid" alt="">
                            </div>
                            <div class="card-footer">
                                <span>Price: <small>{{ p.price }}</small></span>
                                <a @click="addToCart(p)" class="btn btn-sm btn-success float-end">Add to cart</a>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </div>

    </Master>
</template>

<script>
import Master from '@/Layout/Master.vue';
import Loader from '@/Component/Loader.vue';
import axios from 'axios';

export default {
    components: {
        Master,
        Loader
    },
    name: 'ProductPage',
    data() {
        return {
            isload: true,
            products: []
        }
    },
    created() {
        axios.get('https://dummyjson.com/products')
            .then(response => {
                console.log(response.data);
                this.products = response.data.products;
                this.isload = false;
            })
            .catch(error => {
                console.log(error);
                this.isload = false;
            });

    },
    methods: {
        addToCart(p) {
            // console.log(p);
            // Add to cart logic here
            // this.$root.cart.push(p);
            var cart = this.$root.cart;
            cart.push(p);
        }
    }
}
</script>