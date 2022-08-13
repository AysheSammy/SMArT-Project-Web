<template>
    <div class="course">
        <div class="banner"></div>
        <div class="alt_banner">
            <div class="first">
                <img src="./../assets/images/home/course-logo.png" alt="">
                <p>{{ course.isFree == true ? 'Tölegli' : 'Tölegsiz' }}</p>
            </div>
            <h3>{{ course.name }}</h3>
            <p class="course-type"><span></span> {{ course.type }}</p>
            <div class="course-infos">
                <div class="course-info">
                    <h4>Möhleti:</h4>
                    <p>{{ course.durationMonth }} aý</p>
                    <h4>Adam sany:</h4>
                    <p>{{ course.participantNumber }} adam</p>
                </div>
                <div class="course-ingrdnt">
                    <p class="info" v-for="(e, i) in course.ingredients" :key="i">
                        <span></span>
                        {{ e }}
                    </p>
                </div>
            </div>

            <button>Kursa ýazyl</button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        course: {
            type: Object,
            require: true,
        }
    }
}
</script>

<style>
</style>