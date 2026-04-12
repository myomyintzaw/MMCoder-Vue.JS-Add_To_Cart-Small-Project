<template>
    <Master>
        <div class="container mt-5">
            <table class="table table-striped">
                <thead>
                    <tr>
                        <th>Name</th>
                        <th>Image</th>
                        <th>Price</th>
                        <th>Quantity</th>
                        <th>Total</th>
                        <th>Actions</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(p, i) in cart" :key="i">
                        <td>{{ p.title }}</td>
                        <td><img :src="p.thumbnail" alt="" class="img-fluid" style="width: 50px; height: 50px;"></td>
                        <td>${{ (Math.round(p.price * 100) / 100).toFixed(2) }}</td>
                        <td>
                            <div class="d-flex align-items-center">
                                <span @click="reduceQty(p)" class="btn btn-sm btn-danger me-2">-</span>
                                <span class="mx-2">{{ p.qty }}</span>
                                <span @click="addQty(p)" class="btn btn-sm btn-success ms-2">+</span>
                            </div>
                        </td>
                        <td>${{ (Math.round(p.price * p.qty * 100) / 100).toFixed(2) }}</td>
                        <td>
                            <button @click="removeItem(i)" class="btn btn-sm btn-outline-danger">Remove</button>
                        </td>
                    </tr>
                </tbody>
            </table>

            <!-- Grand Total -->
            <div class="row mt-4">
                <div class="col-md-8"></div>
                <div class="col-md-4">
                    <div class="card">
                        <div class="card-body">
                            <h5 class="card-title">Order Summary</h5>
                            <hr>
                            <div class="d-flex justify-content-between">
                                <h6>Grand Total:</h6>
                                <h6>${{ (Math.round(grandTotal * 100) / 100).toFixed(2) }}</h6>
                            </div>
                            <button class="btn btn-primary w-100 mt-3">Checkout</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </Master>
</template>

<script>
import Master from '@/Layout/Master.vue';

export default {
    name: 'CartPage',
    components: {
        Master
    },

    data() {
        return {
            cart: [],
        };
    },
    computed: {
        grandTotal() {
            return this.cart.reduce((total, item) => total + (item.price * item.qty), 0);
        }
    },
    created() {
        this.cart = this.$root.cart;
    },
    methods: {
        addQty(product) {
            if (product.qty >= 1) {
                product.qty++;
                return;
            }

        },
        reduceQty(product) {
            if (product.qty > 1) {
                product.qty--;
            } else {
                // Remove item if quantity reaches 0
                const index = this.cart.findIndex(item => item.title === product.title);
                if (index > -1) {
                    this.cart.splice(index, 1);
                }
            }
        },
        removeItem(index) {
            this.cart.splice(index, 1);
        }
    }
}
</script>