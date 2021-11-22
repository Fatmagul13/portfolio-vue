<template>
  <section id="works" class="bg-works">
    <div class="title">
      <h2>WORKS</h2>
    </div>
    <p>You can reach my project source codes from my <a href="https://github.com/Fatmagul13" target="_blank" style="color:#642afb">github</a> address.</p>
    <carousel :settings="settings" :breakpoints="breakpoints">
      <slide v-for="slide in slides" :key="slide">
        <div class="carousel__item">
          <img :src="getImgUrl(slide.src)" alt="" />
          <div class="overlay">
            <div class="text">{{ slide.description }}</div>
          </div>
        </div>
      </slide>

      <template #addons>
        <navigation />
        <pagination />
      </template>
    </carousel>
  </section>
</template>
<script>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

export default {
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      settings: {
        itemsToShow: 1,
        snapAlign: "center",
        wrapAround:"true",
      },
      breakpoints: {
      // 700px and up
      700: {
        itemsToShow: 1.5,
        snapAlign: 'center',
      },
      // 1024 and up
      1024: {
        itemsToShow: 2.5,
        snapAlign: 'center',
      },
    },
      slides: [
        { src: "vkazan", description: "Vestel Kazan TV App " },
        { src: "Screenshot_2", description: "Weather App" },
        { src: "todo-list", description: "Todo App" },
        { src: "covid-table", description: "Covid Statistics App" },
      ],
    };
  },
  methods: {
    getImgUrl(pet) {
      var images = require.context("../assets/works", false, /\.png$/);
      return images("./" + pet + ".png");
    },
  },
};
</script>
<style lang="scss">
@import "@/styles/works.scss";
</style>