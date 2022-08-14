<template>
  <div class="inputs">
    <div class="content">
      <p class="name">{{$tt('Hasaba alyş formasy', 'Форма регистрации')}}</p>
      <div class="forms">
        <div class="input" v-for="(e, i) in inputs" :key="i">
          <label :for="e.id">{{ $tt(e.label_tm, e.label_ru) }}</label>
          <input :type="e.type" :id="e.id" v-model="models[i]" />
        </div>
        <button @click="submit">{{$tt('Agza bol', 'Регистр')}}</button>
      </div>
      <nuxt-link to="">{{$tt('Ulanyjylary görkez', 'Просмотр пользователей')}}</nuxt-link>
    </div>
  </div>
</template>
  
<script>
export default {
  data() {
    const datas = {
      fname: '',
      email: '',
      age: null,
      gender: '',
      lname: '',
      phone: null,
      job: '',
    }
    const input_values = []

    return {
      models: [
        datas.fname,
        datas.email,
        datas.age,
        datas.gender,
        datas.lname,
        datas.phone,
        datas.job,
      ],
      datas,
      input_values,
      inputs: [
        {
          id: 1,
          label_tm: 'Ady',
          label_ru: 'Имя',
          type: 'text',
        },
        {
          id: 2,
          label_tm: 'Familýasy',
          label_ru: 'Фамилия',
          type: 'text',
        },
        {
          id: 3,
          label_tm: 'Email',
          label_ru: 'Эл. адрес',
          type: 'email',
        },
        {
          id: 4,
          label_tm: 'Telefon nomer',
          label_ru: 'Номер телефона',
          type: 'number',
        },
        {
          id: 5,
          label_tm: 'Ýaşy',
          label_ru: 'Возраст',
          type: 'number',
        },
        {
          id: 6,
          label_tm: 'Gender',
          label_ru: 'Пол',
          type: 'text',
        },
      ],
    }
  },

  methods: {
    submit() {
      this.datas.fname = this.models[0];
      this.datas.email = this.models[1];
      this.datas.age = this.models[2];
      this.datas.gender = this.models[3];
      this.datas.lname = this.models[4];
      this.datas.phone = this.models[5];
      this.datas.job = this.models[6];

      this.input_values.push(this.datas)
      console.log(this.input_values);

      this.datas.fname = '';
      this.datas.email = '';
      this.datas.age = null;
      this.datas.gender = '';
      this.datas.lname = '';
      this.datas.phone = null;
      this.datas.job = '';
    },
  },
}
</script>

<style>
</style>