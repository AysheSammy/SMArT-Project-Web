<template>
    <nav>
        <div class="logo">
            <img src="./../static/Logo.svg" alt="">
        </div>
        <ul class="headerUl">
            <li v-for="(e, i) in links" :key="i" @click="addActive(i)">
                <nuxt-link :to="e.href"  :class="e.active ? 'active' : ''">{{ $tt(e.name_tm, e.name_ru) }}</nuxt-link>
                <!-- <nuxt-link :to="e.href" >{{ $tt(e.name_tm, e.name_ru) }}</nuxt-link> -->
            </li>
        </ul>
        <div class="nav_btns">
            <div class="btn">{{$t('login')}}</div>
            <div class="lang">
                <button class="dropbtn">{{lang}}</button>
                <div class="lang-content">
                    <div v-for="(e, i) in locales" :key="i">
                        <button @click="$i18n.setLocale(e.code)" v-if="e.code != lang">{{e.name}}</button>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            links: [
                {
                    id: 1,
                    name_tm: 'Baş sahypa',
                    name_ru: 'Главный',
                    href: '/',
                    active: false
                },
                {
                    id: 2,
                    name_tm: 'Kurslar',
                    name_ru: 'Курсы',
                    href: '/courses',
                    active: false
                },
                {
                    id: 3,
                    name_tm: 'Gepleşik',
                    name_ru: 'Чат',
                    href: '/chat',
                    active: false
                },
                {
                    id: 4,
                    name_tm: 'Bildirişler',
                    name_ru: 'Уведомления',
                    href: '/notifications',
                    active: false
                },
                {
                    id: 5,
                    name_tm: 'Profil',
                    name_ru: 'Профиль',
                    href: '/profile',
                    active: false
                },

            ]
        }
    },


    
  computed: {
    lang(){
      return this.$i18n.locale
    },
    locales(){
      return this.$i18n.locales
    }
  },

  methods:{
    addActive(id){
        const li = document.querySelectorAll('.headerUl li')
        for(let i =0 ; i< li.length; i++){
            li[i].querySelector('a').classList.remove('active');
        }
        li[id].querySelector('a').classList.add('active');
    }
  }

}
</script>

<style>
</style>