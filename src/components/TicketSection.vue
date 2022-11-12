<template >
    <div class="wrapper">
    <h2>Get your tickets at your nearby cinemas !</h2>
    
        <div class="cinema-wrapper">
           <ul>
            <li  v-for="location in locations" :key="location">
                {{ location }}
                <!-- <test :location='location' /> -->
            </li>
           </ul>
        </div>
    </div>
</template>
<script>
import { cinemaLocs } from '@/assets/data/cinemas';
export default {
    data() {
        return {
            locations : cinemaLocs
        }
    },
}
</script>
<style scoped>
    .wrapper {
        width: 100%;
        color: var(--text-plat);
        /* height: 500px; */
        /* background-color: aqua; */
    }
    
</style>