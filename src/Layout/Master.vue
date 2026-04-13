<template>
    <div>
        <!-- Nav  -->
        <Nav />
        <!-- Nav  -->

        <!-- Content  -->
        <slot></slot>

        <!-- Footer  -->
        <FooterSection />
    </div>
</template>



<script>
import Nav from './Nav.vue';
import FooterSection from './Footer.vue';
export default {
    name: 'MasterLayout',
    components: {
        Nav,
        FooterSection
    }
}
</script>