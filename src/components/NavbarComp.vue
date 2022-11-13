<template>
  <header :class="{ onScroll: !atTop }">
    <div class="left-nav">BLACK PANTHER</div>

    <ul class="right-nav">
      <li>About</li>
      <li>Tickets</li>
      <li>Contact</li>
    </ul>
  </header>
</template>

<script>
export default {
  data() {
    return {
      text: "Halo",
      atTop: true,
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
  },
  beforeMount() {
    document.addEventListener("scroll", this.handleNav);
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
}

ul {
  display: flex;
  list-style: none;
  gap: 3vw;
}
</style>
