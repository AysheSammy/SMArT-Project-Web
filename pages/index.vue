<template>
  <div class="home">
    <div class="hooper">
      <hooper :settings="hooperSettings" group="banner">
        <slide v-for="e in banners" :key="e">
          <div class="slide">
            <img :src="require(`@/assets/images/home/${e.img}`)" alt="">

            <h2>{{$tt(e.subtitle_tm, e.subtitle_ru)}}</h2>
            <h1>{{$tt(e.title_tm, e.title_ru)}}</h1>
            <button>{{$tt(e.btn_tm, e.btn_ru)}}</button>
          </div>
        </slide>

        <hooper-navigation slot="hooper-addons"></hooper-navigation>
        <hooper-pagination slot="hooper-addons"></hooper-pagination>
      </hooper>
    </div>

    <div class="about">
      <div class="title">
        <img src="@/static/Logo.svg" alt="">
        <p>{{ $t('who') }}</p>
      </div>

      <div class="about_content">
        <img src="@/assets/images/home/about-banner.png" alt="">
        <div class="text">{{ $t('about') }}</div>
      </div>

    </div>

    <div class="courses">
      <h2>{{ $t('ourCourses') }}</h2>
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
      <h2>{{ $t('mentors') }}</h2>
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
      banners: [
        {
          img:'banner-img1.png',
          subtitle_tm: 'Gyzlar üçin tölegsiz',
          title_tm: 'Online IT Kurslar',
          btn_tm: 'Kurslary gör',
          subtitle_ru: 'Бесплатно для девушек',
          title_ru: 'Онлайн-курсы по ИТ',
          btn_ru: 'Посмотреть курсы'
        },
        {
          img:'banner-img2.png',
          subtitle_tm: 'Gyzlar üçin tölegsiz',
          title_tm: 'Front-End Web Development Kursy',
          btn_tm: 'Kursa Git',
          subtitle_ru: 'Бесплатно для девушек',
          title_ru: 'Front-End веб-разработка Курсы',
          btn_ru: 'Перейти к курсу'
        },
        {
          img:'banner-img3.png',
          subtitle_tm: 'Gyzlar üçin tölegsiz',
          title_tm: 'Front-End Mobile Development Kursy',
          btn_tm: 'Kursa Git',
          subtitle_ru: 'Бесплатно для девушек',
          title_ru: 'Front-End мобильная разработка Курсы',
          btn_ru: 'Перейти к курсу'
        },
        {
          img:'banner-img4.png',
          subtitle_tm: 'Gyzlar üçin tölegsiz',
          title_tm: 'UI / UX Design Kursy',
          btn_tm: 'Kurslary gör',
          subtitle_ru: 'Бесплатно для девушек',
          title_ru: 'Курсы UI/UX-дизайна',
          btn_ru: 'Перейти к курсу'
        },
        {
          img:'banner-img5.png',
          subtitle_tm: 'Gyzlar üçin tölegsiz',
          title_tm: '3DMax Design Kursy',
          btn_tm: 'Kurslary gör',
          subtitle_ru: 'Бесплатно для девушек',
          title_ru: '3DMax Design КурсыТ',
          btn_ru: 'Перейти к курсу'
        },
      ],
      courses: [
        {
          id: 0,
          name: 'Web Development',
          isFree: true,
          type_tm: 'Başlangyç',
          ingredients: ['HTML', 'CSS', 'JS'],
          participantNumber: 10,
          durationMonth: 3,
          type_ru: 'Новичок',
        },
        {
          id: 1,
          name: 'Mobile Development',
          isFree: true,
          type_tm: 'Başlangyç',
          ingredients: ['Dart', 'Flutter'],
          participantNumber: 10,
          durationMonth: 3,
          type_ru: 'Новичок'
        },
        {
          id: 2,
          name: 'UI / UX Design',
          isFree: true,
          type_tm: 'Başlangyç',
          ingredients: ['Figma', 'Photoshop'],
          participantNumber: 10,
          durationMonth: 3,
          type_ru: 'Новичок'
        },
        {
          id: 3,
          name: '3D Max',
          isFree: true,
          type_tm: 'Beginner',
          ingredients: ['3D max'],
          participantNumber: 10,
          durationMonth: 3,
          type_ru: 'Новичок'
        },
        {
          id: 4,
          name: 'Web Development',
          isFree: false,
          type_tm: 'Intermediate',
          ingredients: ['Vue', 'Nuxt'],
          participantNumber: 10,
          durationMonth: 3,
          type_ru: 'Средний'
        },
        {
          id: 4,
          name: 'Mobile Development',
          isFree: false,
          type_tm: 'Intermediate',
          ingredients: ['Dart Intermediate', 'Flutter Exclusive'],
          participantNumber: 10,
          durationMonth: 3,
          type_ru: 'Средний'
        },
      ],
      mentors: [
        {
          id: 1,
          img: 'mentor1.png',
          fname_tm: 'Söýli',
          lname_tm: 'Atabeýawa',
          job_tm: 'Mobile Developer',
          fname_ru: 'Сойли',
          lname_ru: 'Атабаева',
          job_ru: 'Мобильный разработчик',
        },
        {
          id: 2,
          img: 'mentor1.png',
          fname_tm: 'Ayshe',
          lname_tm: 'Samiyeva',
          job_tm: 'Web Developer',
          fname_ru: 'Айше',
          lname_ru: 'Саммиева',
          job_ru: 'Веб-разработчик',
        },
        {
          id: 3,
          img: 'mentor1.png',
          fname_tm: 'Agamyrat',
          lname_tm: 'Chariyew',
          job_tm: 'Back-End Developer',
          fname_ru: 'Агамырат',
          lname_ru: 'Чарыев',
          job_ru: 'Back-End разработчик',
        },
        {
          id: 4,
          img: 'mentor1.png',
          fname_tm: 'Begench',
          lname_tm: 'Jumayew',
          job_tm: 'Mobile Developer',
          fname_ru: 'Бегенч',
          lname_ru: 'Джумаев',
          job_ru: 'Мобильный разработчик',
        },
        {
          id: 5,
          img: 'mentor1.png',
          fname_tm: 'Merjen',
          lname_tm: 'Saparmyradowa',
          job_tm: 'Web Developer',
          fname_ru: 'Мерджен',
          lname_ru: 'Сапармырадова',
          job_ru: 'Веб-разработчик',
        }
      ],
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
