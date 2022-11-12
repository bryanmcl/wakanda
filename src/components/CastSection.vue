<template>
    <h2>Cast Members</h2>
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
        height: 500px;
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
        margin-left: -100px;
    }

    .card:hover ~.card {
       transform: translateX(100px);
      
    }

    ::-webkit-scrollbar {
        height: 10px;
    }

    ::-webkit-scrollbar-thumb {
        background: var(--text-plat);
        border-radius: 10px;
    }
</style>