<template>
    <nav>
        <div class="logo">
            <img src="./../static/Logo.svg" alt="">
        </div>
        <ul>
            <li v-for="(e, i) in links" :key="i">
                <nuxt-link :to="e.href">{{ e.name_tm }}</nuxt-link>
            </li>
        </ul>
        <div class="nav_btns">
            <div class="btn">Agza bol</div>
            <div class="lang">
                <button class="dropbtn">TM</button>
                <div class="lang-content">
                    <button>RU</button>
                    <button>TM</button>
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
    }

}
</script>

<style>
</style>