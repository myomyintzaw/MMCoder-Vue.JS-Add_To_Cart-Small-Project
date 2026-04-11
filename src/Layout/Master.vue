<template>
    <div>
        <!-- Nav  -->
        <Nav />
        <!-- Nav  -->

        <!-- Content  -->
        <slot></slot>

    </div>
</template>



<script>
import Nav from './Nav.vue';
export default {
    name: 'MasterLayout',
    components: {
        Nav
    }
}
</script>