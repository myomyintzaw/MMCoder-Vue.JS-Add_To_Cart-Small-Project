<!-- <template>
    <div>
        <div class="loader"></div>
    </div>
</template>

<style scoped>
.loader {
    width: 48px;
    height: 48px;
    border: 5px solid #FFF;
    border-bottom-color: #FF3D00;
    border-radius: 50%;
    display: inline-block;
    box-sizing: border-box;
    animation: rotation 1s linear infinite;
}

@keyframes rotation {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}
</style> -->


<template>
    <div class="container text-center-mt-5">
        <div class="spinner-grow text-dark" role="status">
            <!-- <span class="visually-hidden">Loading...</span> -->
            <span class="sr-only">loading...</span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'LoaderComponent'
}
</script>