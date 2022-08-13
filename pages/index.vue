<template>
  <div class="home">
    <div class="hooper">
      <hooper :settings="hooperSettings" group="banner">
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
        <p>kim?</p>
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

    <div class="courses">
      <h2>Kurslarymyz: </h2>
      <div class="course-cards">
        <hooper :settings="courseSetting">
          <slide v-for="(e, i) in courses" :key="i">
            <Course :course="e" />
          </slide>
          <hooper-navigation slot="hooper-addons"></hooper-navigation>
        </hooper>
      </div>
    </div>

    <div class="mentors">
      <h2>Mentorlarymyz:</h2>
      <div class="mentor-cards">
        <hooper :settings="courseSetting">
          <slide v-for="(e, i) in mentors" :key="i">
            <Mentor :info="e" />
          </slide>
          <hooper-navigation slot="hooper-addons"></hooper-navigation>
        </hooper>
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
import Course from '@/components/course-card.vue';
import Mentor from '@/components/mentor-card.vue';

export default {
  data() {
    return {
      courses: [
        {
          id: 0,
          name: 'Web Development',
          isFree: true,
          type: 'Beginner',
          ingredients: ['HTML', 'CSS', 'JS'],
          participantNumber: 10,
          durationMonth: 3,
        },
        {
          id: 1,
          name: 'Mobile Development',
          isFree: true,
          type: 'Beginner',
          ingredients: ['Dart', 'Flutter'],
          participantNumber: 10,
          durationMonth: 3,
        },
        {
          id: 2,
          name: 'UI / UX Design',
          isFree: true,
          type: 'Beginner',
          ingredients: ['Figma', 'Photoshop'],
          participantNumber: 10,
          durationMonth: 3,
        },
        {
          id: 3,
          name: '3D Max',
          isFree: true,
          type: 'Beginner',
          ingredients: ['3D max'],
          participantNumber: 10,
          durationMonth: 3,
        },
        {
          id: 4,
          name: 'Web Development',
          isFree: false,
          type: 'Intermediate',
          ingredients: ['Vue', 'Nuxt'],
          participantNumber: 10,
          durationMonth: 3,
        },
        {
          id: 4,
          name: 'Mobile Development',
          isFree: false,
          type: 'Intermediate',
          ingredients: ['Dart Intermediate', 'Flutter Exclusive'],
          participantNumber: 10,
          durationMonth: 3,
        },
      ],
      mentors: [
        {
          id: 1,
          img: 'mentor1.png',
          fname: 'Söýli',
          lname: 'Atabeýawa',
          job: 'Mobile Developer'
        },
        {
          id: 2,
          img: 'mentor1.png',
          fname: 'Ayshe',
          lname: 'Samiyeva',
          job: 'Web Developer'
        },
        {
          id: 3,
          img: 'mentor1.png',
          fname: 'Agageldi',
          lname: 'Pylaniyew',
          job: 'Back-End Developer'
        },
        {
          id: 4,
          img: 'mentor1.png',
          fname: 'Begench',
          lname: 'Jumayew',
          job: 'Mobile Developer'
        },
        {
          id: 5,
          img: 'mentor1.png',
          fname: 'Geldimyrat',
          lname: 'Chashemow',
          job: 'Web Developer'
        },
        {
          id: 6,
          img: 'mentor1.png',
          fname: 'Merjen',
          lname: 'Saparowa',
          job: 'Mobile Developer'
        }
      ]
    }
  },
  components: {
    Hooper,
    Slide,
    HooperPagination,
    HooperNavigation,
    Course,
    Mentor
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
    },
    courseSetting() {
      const settings = {
        infiniteScroll: false,
        wheelControl: false,
        breakpoints: {
          800: {
            centerMode: false,
            itemsToShow: 2
          },
          1000: {
            itemsToShow: 4,
            pagination: 'fraction'
          }
        }
      }
      return settings;
    }
  }
};
</script>
