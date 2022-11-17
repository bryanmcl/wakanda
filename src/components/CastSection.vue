<template>
    <h2 id="cast">Cast Members</h2>
    <div class="wrapper">

        <CardComp class="card" v-for="(cast, index) in casts" :key = 'index' :cast = 'cast' />
        <!-- <button @click="test">CLICK</button> -->
    </div>
</template>

<script>
import { castArray } from '@/assets/data/cast';
import CardComp from "./CardComp.vue";

export default {
    components: {
        CardComp
    },
    methods : {
        test(){
            console.log(this.casts)
        }
    },
    data(){
        return {
            casts : castArray
        }
    }
}
</script>

<style scoped>
    .wrapper {
        margin: 15px 30px;
        height: clamp(350px, 40vw, 600px);
        display: flex;
        justify-content: center;
        align-items: center;
        overflow-x: scroll;
        gap: 1rem;

        
    }


    h2 {
        text-align:center;
        font-weight: bold;
        font-size: 3rem;
        font-family: 'Inter', sans-serif;
        margin-top: 2rem;

        color: var(--text-plat);

    }

    .card {
        transition: all 0.5s ease;
    }


    .card:hover {
        transform: translateY(-1rem);
    }
    .card:not(:first-child){
        margin-left: -10vw;
    }

    .card:hover ~.card {
       transform: translateX(10vw);
      
    }

    ::-webkit-scrollbar {
        height: 10px;
    }

    ::-webkit-scrollbar-thumb {
        background: var(--text-plat);
        border-radius: 10px;
    }

    @media screen and (max-width: 800px){
        .wrapper {
            flex-direction: column;
            height: fit-content!important;
        }

        .card {
        transition: all 0.5s ease;
        }


        .card:hover {
            transform: none;
        }
        .card:not(:first-child){
            margin-left: 0;
        }

        .card:hover ~.card {
            transform: none;
        
        }
    }
</style>