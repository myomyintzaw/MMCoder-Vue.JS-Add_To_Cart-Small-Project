<template>
    <div>
        <Master>
            <div class="jumbotron mt-5 mx-5 mb-5 p-5 ">
                <h2 class="display-4">Hello, Guy!</h2>
                <h3 class="text-primary">Welcome to Our Store</h3>
                <p class="lead">
                    <!-- This is a simple hero unit, a simple jumbotron-style component for calling extra attention to featured content or information. -->
                    Discover amazing products at unbeatable prices. Shop smarter, faster, and easier with our seamless
                    experience.
                </p>
                <hr class="my-4">
                <p>
                    <!-- It uses utility classes for typography and spacing to space content out within the larger container. -->
                    Browse our latest collections and add your favorite items to your cart with just one click.
                </p>
                <h4 class="lead">Happy Shopping!/Call to Action</h4>

                <h4 class="lead">Start Shopping Now</h4>
                <br>
                <h3>🛍️ Featured Products Section</h3>
                <p class="lead">Check out our latest products and deals!<br>Featured Products
                    Handpicked items just for you. Click “Add to Cart” to save them instantly.</p>
                <br>
                <h2>⚡ Why Shop With Us</h2>
                <ul>
                    <li>Fast & Free Shipping</li>
                    <li>Easy 30-Day Returns</li>
                    <li>Fast and secure checkout</li>
                    <li>24/7 Customer Support</li>
                    <li>Quality Guaranteed</li>
                    <li>Friendly customer support</li>
                </ul>
                <br>
                <h2>🛒 Cart Reminder Banner</h2>
                <p>Don't forget to check your cart before you leave!<br>
                    Your cart is just a click away. Review your items anytime and complete your purchase..
                    <!-- بسهولة. -->
                <a href="#" class="btn btn-primary">View Cart</a>
                </p>
                <a class="btn btn-primary btn-lg" href="#" role="button">Learn more</a>
            </div>
        </Master>
    </div>
</template>

<script>
import Master from '@/Layout/Master.vue';
export default {
    components: {
        Master
    },
    name: 'HomePage'
}
</script>