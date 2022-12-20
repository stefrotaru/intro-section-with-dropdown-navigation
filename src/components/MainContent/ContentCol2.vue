<template>
    <div class="col-2">
        <img src="../../assets/image-hero-desktop.png" alt="">
    </div>
</template>

<script>
export default {
    name: 'ContentCol2',
}
</script>

<style>
.col-2 {
    text-align: center;
}

.col-2 > img {
    height: 75vh;
}

@media (max-width: 960px) {
    .col-2 > img {
        content: url(../../assets/image-hero-mobile.png);
        padding-block-start: 2rem;
        width: 100%;
        height: auto;
    }
}
</style>