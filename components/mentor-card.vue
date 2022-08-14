<template>
  <div class="mentor">
    <img :src="require(`@/assets/images/home/${info.img}`)" alt="">
    <p class="name">{{$tt(info.fname_tm, info.fname_ru)}}</p>
    <p class="name">{{$tt(info.lname_tm, info.lname_ru)}}</p>
    <p class="job">{{$tt(info.job_tm, info.job_ru)}}</p>
  </div>
</template>

<script>
export default {
props: {
    info: {
        type: Object,
        require: true,
    }
}
}
</script>

<style>

</style>