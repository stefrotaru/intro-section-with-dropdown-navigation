<template>
    <div class="col-1 landing">
        <h1 class="landing__title">Make remote work</h1>
        <p class="landing__description">Get your team in sync, no matter your location. Streamline processes, create team rituals, and watch producitvity soar.</p>
        <button class="landing__btn">Learn more</button>
        <div class="landing__icons">
            <img src="../../assets/client-databiz.svg" alt="databiz">
            <img src="../../assets/client-audiophile.svg" alt="audiophile">
            <img src="../../assets/client-meet.svg" alt="meet">
            <img src="../../assets/client-maker.svg" alt="maker">
        </div>
    </div>
</template>

<script>
export default {
    name: 'ContentCol1',
}
</script>

<style>
.col-1 {
    
    display: flex;
    flex-direction: column;
    justify-self: center;
    place-content: space-between;
    width: 35vw;
}
.landing__title {
    padding-block-start: 4rem;
    font-size: 4.7rem;
}
.landing__description {
    font-size: 1.1rem;
    line-height: 1.8rem;
    color: hsl(0, 0%, 41%);
}
.landing__btn {
    align-self: flex-start;
    border-radius: 1rem;
    background: black;
    color: white;
    font-size: 1.3rem;
    padding: 1rem 1.6rem;
}
.landing__btn:hover {
    background: transparent;
    color: black;
}
.landing__icons {
    height: 20px;
    display: flex;
    justify-content: space-between;
}
.landing__icons > img:nth-child(2) {
    height: 32px;
}
.landing__icons > img:nth-child(4) {
    height: 25px;
}

@media (max-width: 960px) {
    .col-1 {
        align-self: center;
        text-align: center;
        width: unset;
        gap: 2rem;
        padding: 1rem;
    }

    .landing__title {
        padding-block-start: .5rem;
        font-size: calc(1.5rem + 3vw);
    } 
    
    .landing__description {
        font-size: 1rem;
    }

    .landing__btn {
        align-self: center;
    }

    .landing__icons {
        display: flex;
        justify-content: space-between;
    }
    .landing__icons > img {
        height: calc(8px + 1.5vw);
        width: auto;
    }
    .landing__icons > img:nth-child(2) {
        height: calc(16px + 1.5vw);
        width: auto;
    }
    .landing__icons > img:nth-child(4) {
        height: calc(16px + 1.5vw);
        width: auto;
    }
}
</style>