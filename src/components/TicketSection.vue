<template >
    <div class="wrapper">
    <h2>Get your tickets at your nearby cinemas !</h2>
    
        <div class="cinema-wrapper">
           <!-- <ul> -->
            <li id="liCinema" :class="{'removeAnimation': removeAnimation}" v-for="(location, index) in locations" :key="index" :style="{'--order': index}">
            <a href="https://www.cgv.id/en/movies/info/22025100" target="_blank">
                {{ location }}
            </a>
                <!-- <test :location='location' /> -->
            </li>
           <!-- </ul> -->
        </div>
    </div>
</template>
<script>
import { cinemaLocs } from '@/assets/data/cinemas';
export default {
    data() {
        return {
            locations : cinemaLocs,
            removeAnimation: false
        }
    },
    methods: {
        removeTransition(w) {
            if(w.matches){
                this.removeAnimation = true
            }
            else {
                this.removeAnimation = false
            }
        }
    },
    beforeMount() {
        let w = window.matchMedia("(max-width: 900px)");
        this.removeTransition(w)
        w.addEventListener('change', this.removeTransition)
    },
}
</script>
<style scoped>
    .wrapper {
        width: 100%;
        color: var(--text-plat);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        font-family: 'Inter', sans-serif;

        
        /* height: 500px; */
        /* background-color: aqua; */
    }

    .wrapper > h2 {
        font-size: 2.5rem;
        margin: 50px 30px;
        text-align: center;

    }

    li {
        text-align: center;
        font-size: 2rem;
        animation: test 1s infinite alternate;
        animation-delay: calc(var(--order)*1000ms);
    }

    li > a {
        text-decoration: none !important;
        color: var(--text-plat);
    }

    li:hover {
        animation-play-state: paused;
    }

    @keyframes test {
        from {
            transform: translateY(0);
        }
        to {
            transform: translateY(-2rem);
        }
    }
    .cinema-wrapper {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 1rem;
        text-decoration: none !important;
    }

    .cinema-wrapper :nth-child(1) {
        list-style: none;
    }

    .removeAnimation {
        animation: none;
    }

    @media screen and (max-width: 900px) {
        .cinema-wrapper {
            flex-direction: column;
            list-style: none;
        }

        li {
            /* animation: none; */
        }
    
    
    }
      
</style>