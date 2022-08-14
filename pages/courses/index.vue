<template>
    <section class="courses">
        <Category :categories="categories" @globalUl="showCategory" @childId="showCourse" />
        <div class="course-cardlar">
            <Course v-for="(e, i) in categories[category_id].course[course_id].card" :key="i" :course="e" />
        </div>
    </section>
</template>

<script>
import Category from '@/components/course-category.vue';
import Course from '@/components/course-card.vue';
export default {
    components: {
        Category,
        Course
    },
    data() {
        return {
            categories: [
                {
                    name: 'Programirleme',
                    course: [
                        {
                            categ_tm: 'Programirleme esasy',
                            categ_ru: 'Программирование является базовым',
                            card: [
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
                            ]
                        },
                        {
                            categ_tm: 'Web development',
                            categ_ru: 'веб-разработка',
                            card: [
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
                                    id: 4,
                                    name: 'Web Development',
                                    isFree: false,
                                    type_tm: 'Intermediate',
                                    ingredients: ['Vue', 'Nuxt'],
                                    participantNumber: 10,
                                    durationMonth: 3,
                                    type_ru: 'Средний'
                                },
                            ]
                        },
                        {
                            categ_tm: 'Mobile development',
                            categ_ru: 'Мобильная разработка',
                            card: [
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
                                    id: 4,
                                    name: 'Mobile Development',
                                    isFree: false,
                                    type_tm: 'Intermediate',
                                    ingredients: ['Dart Intermediate', 'Flutter Exclusive'],
                                    participantNumber: 10,
                                    durationMonth: 3,
                                    type_ru: 'Средний'
                                },
                            ]
                        },
                    ],
                },
                {
                    name: 'Design',
                    course: [
                        {
                            categ_tm: 'UI / UX Design',
                            categ_ru: 'UI / UX-дизайн',
                            card: [
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
                            ]
                        },
                        {
                            categ_tm: '3D Max',
                            categ_ru: '3D Max',
                            card: [
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
                            ]
                        }


                    ]
                }
            ],
            category_id: 0,
            course_id: 0,
        }
    },
    methods: {
        showCategory(id) {
            this.category_id = id;
        },
        showCourse(id) {
            this.course_id = id;
        }
    }
}
</script>

<style>
</style>