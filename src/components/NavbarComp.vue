<template>
  <header :class="{ onScroll: !atTop }">
    <div class="left-nav"> <a href="#hero">BLACK PANTHER</a></div>

    <span @click="toggleDrop" class="borgar material-symbols-outlined">menu</span>
    <ul v-show="showDrop" class="dropdown">
      <li><a href="#about">Overview</a></li>
      <li><a href="#cast">Casts</a></li>
      <li><a href="#ticket">Contact</a></li>
    </ul>
    
    <ul class="right-nav">
      <li><a href="#about">Overview</a></li>
      <li><a href="#cast">Casts</a></li>
      <li><a href="#ticket">Ticket</a></li>
    </ul>
  </header>
</template>

<script>

export default {
  data() {
    return {
      text: "Halo",
      atTop: true,
      showDrop: false
    };
  },
  methods: {
    handleNav() {
      if (window.pageYOffset > 0) {
        if (this.atTop) this.atTop = false;
      } else {
        if (!this.atTop) this.atTop = true;
      }
    },
    // showDropdown() {
    //   let drop = document.querySelector('.dropdown')
    //   drop.classList.toggle('visible')
    // },
    toggleDrop(){
      if (this.showDrop) this.showDrop = false;
      else if (!this.showDrop) this.showDrop = true;
    }
  },
  beforeMount() {
    document.addEventListener("scroll", this.handleNav);

    window.addEventListener("resize", ()=>{
      if(window.matchMedia("(min-width: 530px)").matches){
        // alert("WOI")
        this.showDrop = false
        // this.toggleDrop()
      }
    })
  },
};
</script>

<style scoped>
header {
  box-sizing: border-box;
  position: fixed;
  display: flex;
  align-items: center;
  justify-content: space-between;

  padding: 0 2rem;
  height: 5rem;
  width: 100%;
  /* background-color: var(--primary-black); */
  color: var(--text-plat);

  transition: all 0.5s ease;
  z-index: 2;
}

header.onScroll {
  background-color: var(--primary-black);
}

.left-nav {
  font-family: "Press Start 2P", cursive;
}

.right-nav {
    font-family: 'Inter', sans-serif;
    display: flex;
    list-style: none;
    gap: 3vw;
  }

.borgar {
  display: none;
}

.dropdown {
  position: absolute;
  bottom: -9.65rem;
  left: 0;
  /* flex-direction: column; */
  background: var(--bdazzled-blue);

  list-style: none;
  width: 100%;
}

.dropdown li a {
  display: block;
  width: 100%;
  padding: 1rem;
}

.dropdown li:hover {
  background: var(--nippon-paint);
}

.visible {
  display: flex !important;
  flex-direction: column;
  /* justify-content: flex-end; */
  text-align: center;
}

.dropdown li {
  font-family: 'Inter', sans-serif;
  /* font-size: 2rem; */
  
  
}

a {
  text-decoration: none;
  color: var(--text-plat);
}

@media screen and (max-width: 530px) {
  .right-nav {
    display: none;
  }
  .borgar {
    display: block;
  }
}
</style>
