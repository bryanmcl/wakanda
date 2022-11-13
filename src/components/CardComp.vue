<template>
    <div class="card">
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
    flex-direction: column;
    justify-content: flex-end;
    min-width: 200px;
    width: 20vw;
    aspect-ratio: 3/4;
    z-index: 1;

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
    font-size: clamp(1rem, 2.5vw ,2rem);
    margin-left: 20px;
    text-shadow: 1px 1px 3px rgb(55, 55, 55);
}

.role  {
    font-size: clamp(0.5rem, 1.5vw ,1rem);
    margin-left: 20px;
    margin-bottom: 1rem;
    text-shadow: 1px 1px 3px rgb(55, 55, 55);
}

.card:hover img{
    transform: scale(1.25) rotateZ(10deg);
    filter: grayscale(100%) brightness(0.8);
}

@media screen and (max-width: 800px){
    .card {
        width: 50vw;
    }

    .name {
        font-size: clamp(1rem, 4vw ,4rem);
    }

    .role  {
        font-size: clamp(1rem, 2.5vw ,2rem);
    }

}
    
</style>