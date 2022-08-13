<template>
  <div class="mentor">
    <img :src="require(`@/assets/images/home/${info.img}`)" alt="">
    <p class="name">{{info.fname}}</p>
    <p class="name">{{info.lname}}</p>
    <p class="job">{{info.job}}</p>
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