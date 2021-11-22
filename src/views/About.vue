<template>
    <section id="about"  class="hero">
      <div class="title">
        <h2>ABOUT ME</h2>
      </div>
      <div class="hero-text container">
        <div class="section-content">
          <div class="container-fluid">
            <div class="row justify-content-center">
              <div class="photo">
                <a>
                  <img src="../assets/profile-pic.jpg" alt="photo" />
                </a>
              </div>
            </div>
            <div class="row">
              <div class="col-md-7 mr-auto card-mobile">
                <div class="paragraph">
                  <h3 style="font-weight:800; letter-spacing:2px">{{ myInfo.name }}</h3>
                  <div  class="begin">{{ myInfo.job }}</div>
                  <br />
                  <p>{{ myInfo.description }}</p>
                </div>
              </div>
              <div class="col-md-4 card-mobile"></div>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      myInfo: {
        name: "FATMA GUL YURTSEVEN",
        job: "Frontend Developer",
        description:"I am a Frontend Developer in Bursa, Turkey. I graduated from Kutahya Dumlupınar University Computer Engineering Department. I am developing website frontends with Vue.js framework. I am developing admin panel and dashboard screens for the needs of the company. I developed the VKazan tv application for Vestel smart televisions. I developed games for the browser with Phaser.js."
      },
      //    "Lorem ipsum dolor sit amet consectetur, adipisicing elit.Natus modi possimus esse officia debitis, corporis, quidem ratione necessitatibus repudiandae adipisci magni. Rerum ab necessitatibus officiis sunt, nisi esse quo voluptatem? Saepe rem, at repellat est, quaerat enim asperiores error dignissimos necessitatibus eveniet iure dolore, incidunt officiis. Possimus a ipsa quidem. Commodi minima, voluptatibus nisi quis ex quidem quo doloremque non placeat, rem sapiente. Cumque aspernatur quis sunt a numquam consectetur maxime, est ipsam in omnis culpa quam assumenda excepturi, laudantium et aliquid veniam explicabo iusto asperiores suscipit exercitationem modi eveniet ab. Veniam quibusdam, a nisi soluta culpa vel aspernatur magnam!",
      
    };
  },
  components: {},
};
</script>

<style lang="scss" scoped>
@import "@/styles/constants.scss";
@import "@/styles/about.scss";
</style>