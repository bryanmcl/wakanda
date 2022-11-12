<template>
    <div class="card" :style="{'z-index': '1'}">
        <img :src= "require(`../assets/casts/${cast.img}`)" alt="">
        <div class="name">{{cast.name}}</div>
        <div class="role">{{cast.role}}</div>
    </div>
</template>

<script>
export default {
    props :['cast'],
    // computed :{
    //     zIndex(){
    //         return 
    //     }
    // }

}
</script>

<style>
.card {
    position: relative;
    display: flex;
    flex-grow: 0;
    flex-direction: column;
    justify-content: flex-end;
    min-width: 300px;
    width: 20vw;
    height: 400px;

    /* background: var(--secondary); */
    color: var(--text-plat);
    border-radius: 10px;
    overflow: hidden;

    box-shadow: -1rem 0 1.5rem rgba(0, 0, 0, 0.768);
}

.card img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: -1;
    transition: all 0.5s ease;

    /* filter: brightness(0.5); */
}

.name {
    font-size: 2rem;
    margin-left: 20px;
    text-shadow: 1px 1px 3px rgb(55, 55, 55);
}

.role  {
    font-size: 1rem;
    margin-left: 20px;
    margin-bottom: 1rem;
    text-shadow: 1px 1px 3px rgb(55, 55, 55);
}

.card:hover img{
    transform: scale(1.25) rotateZ(10deg);
    filter: grayscale(100%) brightness(0.8);
}
    
</style>