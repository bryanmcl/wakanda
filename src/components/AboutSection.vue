<template>
    <div class="wrapper">
        <div class="text-wrapper">
            <h2>Overview</h2>
            <span class="description">
                Queen Ramonda (Angela Bassett), Shuri (Letitia Wright), M’Baku (Winston Duke), Okoye (Danai Gurira) and
                the Dora Milaje (including Florence Kasumba), fight to protect their nation from intervening world
                powers in the wake of King T’Challa’s death. As the Wakandans strive to embrace their next chapter, the
                heroes must band together with the help of War Dog Nakia (Lupita Nyong’o) and Everett Ross (Martin
                Freeman) and forge a new path for the kingdom of Wakanda.
            </span>

            <h3>Director</h3>
            <span class="director">
                Ryan Coogler
            </span>

            <h3>Writer</h3>
            <span class="writer">
                Ryan Coogler
            </span>

            <h3>Release Date</h3>
            <span class="release">
                Nov 11, 2022
            </span>


        </div>

        <img src="../assets/poster.jpg" alt="">
    </div>
</template>
<script>
export default {

}
</script>
<style scoped>
.wrapper {
    margin: 50px 0;
    /* height: min-content; */
    width: 100%;
    display: flex;
    justify-content: space-around;
}

.wrapper img {
    min-width: 15rem;
    width: 30vw;
    height: fit-content;
}

.text-wrapper {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    color: var(--text-plat);
    /* margin-left: 15px; */
    font-family: 'Inter', sans-serif;

    justify-content: center;
}

.text-wrapper>span {
    width: 40vw;
    opacity: 0.8;
    text-align: justify;
}

@media screen and (max-width:600px) {
    .wrapper {
        flex-direction: column-reverse;
        justify-content: center;
        align-items: center;
        gap: 5rem;
        text-align: center;
    }

    .text-wrapper>span {
        width: 80vw;
        text-align: center;
    }
}


</style>