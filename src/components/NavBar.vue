<template>
  <nav id="navbar" :class="{ 'navbar--dark': darkToggle }">
    <div class="navbar__logo">
      <i class="fab fa-vuejs"></i>
      <a href="javascript:;">David</a>
    </div>
    <ul class="navbar__menu" :class="{ open: mobileToggle }">
      <li
        class="navbar__menu__item"
        v-for="(item, idx) in navbarItems"
        :key="idx"
        :data-link="item.hashLink"
        @click="hashMove"
      >
        {{ item.name }}
      </li>
    </ul>
    <button class="navbar__toggle-btn" @click="mobileToggle = !mobileToggle">
      <i class="fas fa-bars"></i>
    </button>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      mobileToggle: false,
      darkToggle: false,
      navbar: null,
      navbarHeight: null,
      homeContainer: null,
      homeHeight: null,
      navbarItems: [
        { hashLink: "#home", name: `Home` },
        { hashLink: "#about", name: `About` },
        { hashLink: "#skills", name: `Skills` },
        { hashLink: "#work", name: `My work` },
        { hashLink: "#testimonials", name: `Testimonial` },
        { hashLink: "#contact", name: `Contact` }
      ]
    };
  },
  methods: {
    hashMove(e) {
      const navbarMenu = document.querySelector(".navbar__menu");
      const hashValue = e.target.dataset.link;
      if (this.$route.hash == hashValue) {
        return false;
      }
      navbarMenu.classList.remove("open");
      this.$router.push(hashValue);
    },
    setNabarHeight() {
      this.navbar = document.querySelector("#navbar");
      this.navbarHeight = this.navbar.getBoundingClientRect().height;
    },
    setHomeContainerHeight() {
      this.homeContainer = document.querySelector(".home__container");
      this.homeHeight = this.homeContainer.getBoundingClientRect().height;
    },
    homeContainerScroll() {
      document.addEventListener("scroll", () => {
        this.homeContainer.style.opacity = 1 - window.scrollY / this.homeHeight;
      });
    },
    navbarToggle() {
      document.addEventListener("scroll", () => {
        if (window.scrollY > this.navbarHeight) {
          this.darkToggle = true;
        } else {
          this.darkToggle = false;
        }
      });
    }
  },
  mounted() {
    this.setNabarHeight();
    this.navbarToggle();
    this.setHomeContainerHeight();
    this.homeContainerScroll();
  }
};
</script>

<style></style>
