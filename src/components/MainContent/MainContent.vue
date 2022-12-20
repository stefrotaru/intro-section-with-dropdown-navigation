<template>
    <div class="container">
        <ContentCol1/>
        <ContentCol2/>
    </div>
</template>

<script>
import ContentCol1 from './ContentCol1.vue';
import ContentCol2 from './ContentCol2.vue';

export default {
    name: 'MainContent',
    components : {
        ContentCol1,
        ContentCol2,
    }
}
</script>

<style>
.container {
    width: 100%;
    height: 50%;
    padding: 2.5rem 5rem;

    align-self: center;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1rem;
}

@media (max-width: 960px) {
    .container {
        padding: unset;

        display: flex;
        flex-direction: column-reverse;
    }
}
</style>