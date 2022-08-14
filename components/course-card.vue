<template>
    <div class="course">
        <div class="banner"></div>
        <div class="alt_banner">
            <div class="first">
                <img src="./../assets/images/home/course-logo.png" alt="">
                <p>{{ course.isFree == true ? $t('free') : $t('notFree') }}</p>
            </div>
            <h3>{{ course.name }}</h3>
            <p class="course-type"><span></span> {{ $tt('type_tm', 'type_ru') }}</p>
            <div class="course-infos">
                <div class="course-info">
                    <h4>{{$t('duration')}}:</h4>
                    <p>{{ course.durationMonth }} {{$t('month')}}</p>
                    <h4>{{$t('num_people')}}:</h4>
                    <p>{{ course.participantNumber }} {{$t('people')}}</p>
                </div>
                <div class="course-ingrdnt">
                    <p class="info" v-for="(e, i) in course.ingredients" :key="i">
                        <span></span>
                        {{ e }}
                    </p>
                </div>
            </div>

            <button>{{$t('sign_course')}}</button>
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