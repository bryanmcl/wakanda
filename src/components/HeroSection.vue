<template>
    <div class="wrapper">
        <div class="bg"></div>
        <span>Black Panther</span>
        <iframe class="video" src="https://www.youtube.com/embed/_Z3QKkl1WyM?controls=0&loop=1&autoplay=1&mute=1&rel=0&playlist=_Z3QKkl1WyM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; loop" allowfullscreen></iframe>
      </div>
</template>

<script>
export default {
    
    
}
</script>

<style scoped>

    body {
        font-family: 'Inter', sans-serif;
    }

    .wrapper {
        display: flex;
        position: relative;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .wrapper > span {
        text-transform: uppercase;
        font-weight: bold;
        text-align: center;
        color: var(--text-plat);
        font-family: 'Inter', sans-serif;
        letter-spacing: 2px;
        /* font-size: 5rem; */
        font-size: clamp(2rem ,5vw, 5rem);
    }

    .bg {
        position: absolute;
        background-image: url('../assets/blackpanther.jpg');
        background-size: cover;
        /* background: var(--primary-black); */
        height: 100vh;
        width: 100%;
        z-index: -1;
        filter: brightness(0.5);
    }

    .video {
        /* position: absolute;
        top: 50%;
        left: 50%;
        transform: translateX(-50%);
        transform: translateY(-50%); */

        aspect-ratio: 16/9;
        min-width: 15rem;
        width: 50vw;
    }

    /* .bg::after {
        
    } */
</style>