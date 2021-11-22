<template>
  <header :class="{ 'scrolled-nav': scrolledNav }">
    <nav>
      <div class="branding">
        <img src="@/assets/letter-f.png" alt="" />
      </div>
      <ul v-show="!mobile" class="navigation">
        <li>
          <a class="nav-item link" href="#about">About</a>
        </li>
        <li>
          <a class="nav-item link" href="#works" >Works</a>
        </li>
        <li>
          <a class="nav-item link" href="#comments" >Comments</a>
        </li>
        <li>
          <a class="nav-item link" href="#contact">Contact</a>
        </li>
      </ul>
      <div class="icon">
        <i
          @click="toggleMobilNav"
          v-show="mobile"
          class="far fa-bars"
          :class="{ 'icon-active': mobileNav }"
        ></i>
      </div>

      <transition name="mobile-nav">
        <ul v-show="mobileNav" class="dropdown-nav">
          <li>
            <a class="nav-item link" href="#about">About</a>
          </li>
          <li>
            <a class="nav-item link" href="#works">Works</a>
          </li>
          <li>
            <a class="nav-item link" href="#comments">Comments</a>
          </li>
          <li>
            <a class="nav-item link" href="#contact">Contact</a>
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script>
export default {
  name: "navigation",
  data() {
    return {
      scrolledNav: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
  methods: {
    scrollToComments() {
      this.$scrollPosition(document.getElementById("comments"), 800);
    },
    toggleMobilNav() {
      this.mobileNav = !this.mobileNav;
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 750) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },
    updateScroll() {
      const scrollPosition = window.scrollY;
      if (scrollPosition > 50) {
        this.scrolledNav = true;
        return;
      }
      this.scrolledNav = false;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/styles/navigation.scss";
</style>
