<template>
    <div class="categories">
        <p>{{ $t('category_title') }}</p>
        <div class="dropdowns" v-for="(e, i) in categories" :key="i" @click="showCateg(i)">
            <div>
                <img src="~/assets/images/arrow.png" class="arrow-image">
                <h4>{{ e.name }}</h4>
            </div>
            <ul class="categ">
                <li v-for="(a, i) in e.course" :key="i" class="cat" @click="liler(i)">
                    <p>{{ $tt(a.categ_tm, a.categ_ru) }}</p>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            globalUl: 0,
        }
    },
    props: {
        categories: {
            type: Array,
            require: true,
        }
    },
    methods: {
        showCateg(id) {
            this.globalUl = id;
            const categ = document.querySelectorAll('.categ')
            for (let i = 0; i < categ.length; i++) {
                categ[i].style.display = 'none';
                // listItems[i].classList.add('block');
            }
            let img = document.querySelectorAll('.arrow-image')
            for (let i = 0; i < img.length; i++) {
                img[i].classList.remove('down')
            }
            img[id].classList.add('down')
            categ[id].style.display = 'block';
        },
        liler(id) {
            this.$emit('globalUl', this.globalUl);
            this.$emit('childId', id);
            console.log(this.globalUl, id);
        }
    }
}
</script>

<style>
</style>