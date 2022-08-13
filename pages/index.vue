<template>
  <div class="home">
    <div class="hooper">
      <hooper :settings="hooperSettings">
        <slide>
          <div class="slide">

          </div>
        </slide>
        <slide>
          <div class="slide">

          </div>
        </slide>
        <slide>
          <div class="slide">

          </div>
        </slide>

        <hooper-navigation slot="hooper-addons"></hooper-navigation>
        <hooper-pagination slot="hooper-addons"></hooper-pagination>
      </hooper>
    </div>

    <div class="about">
      <div class="title">
        <img src="@/static/Logo.svg" alt="">
        <p>kim???</p>
      </div>
      <div class="about_content">
        <img src="@/assets/images/home/about-banner.png" alt="">
        <div class="text">
          Zenanlaryň hukuklaryny we mümkinçiliklerini giňeltmek maksady bilen, aýal-gyzlaryň bilim almagyna, dowamly
          kämilleşmegine, kär saýlamaga, hünär taýýarlygyna goldaw berýän online okuw merkezi. Mundan başga-da üstünikli
          tamamlan uçurumlarymyzy işe ýerleşmäge kömek edýäris.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {
  Hooper, Slide, Pagination as HooperPagination,
  Navigation as HooperNavigation
} from 'hooper';
import 'hooper/dist/hooper.css';

export default {
  components: {
    Hooper,
    Slide,
    HooperPagination,
    HooperNavigation
  },
  computed: {
    hooperSettings() {
      const settings = {
        itemsToShow: 1,
        centerMode: false,
        autoPlay: true,
        playSpeed: 5000,
        transition: 1100,
        hoverPause: false,
        infiniteScroll: true,
        wheelControl: false,
      }
      return settings
    }
  }
};
</script>
