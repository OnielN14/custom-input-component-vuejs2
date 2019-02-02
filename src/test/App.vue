<template>
  <div id="app">
    <form @submit.prevent="submit">

      <checkbox v-for="(item, index) in checkboxHobby.data" :id="checkboxHobby.name+index" :key="index" :nameGroup="checkboxHobby.name" :values="item.value" :label="item.label" v-model="selectedHobi"></checkbox>
      <!-- <radio-block v-model="selectedAgama" :blockTitle="radioAgama.title" :radioData="radioAgama"></radio-block>

      <checkbox-block v-model="checkboxHobby" :blockTitle="checkboxHobby.title" :checkboxData="checkboxHobby"></checkbox-block> -->

      <!-- <button type="button" name="btnKirim" @click="submit">Kirim</button> -->
    </form>

    <div class="">
      <!-- Agama : {{selectedAgama}} -->
      Selected : {{selectedHobi}}
    </div>
  </div>
</template>

<script>
import Checkbox from '../components/custom-input/input-checkbox-component.vue'

import RadioBlock from '../components/block-custom-radio-component.vue'
import CheckboxBlock from '../components/block-custom-checkbox-component.vue'

export default {
  name: 'app',
  components: {
    Checkbox,
    CheckboxBlock,
    RadioBlock
  },
  data(){
    return {
      selectedAgama : '',
      selectedHobi : '',
      radioGender : {
        title : 'Jenis Kelamin',
        name : 'gender',
        data : [
          { value : 0, label : 'Laki-laki'},
          { value : 1, label : 'Perempuan'},
        ]
      },
      radioAgama : {
        title : 'Agama',
        name : 'agama',
        data : [
          { value : 0, label : 'Islam'},
          { value : 1, label : 'Kristen Katolik'},
          { value : 2, label : 'Kristen Protestan'},
          { value : 3, label : 'Buddha'},
          { value : 4, label : 'Hindu'},
          { value : 5, label : 'Konghucu'},
        ]
      },
      checkboxHobby : {
        title : 'Hobi',
        name : 'hobi',
        data : [
          { value : 0, label : 'Baca Manga'},
          { value : 1, label : 'Stalking Mantan'},
          { value : 2, label : 'Main Game'},
          { value : 3, label : 'Bikin Gambar'}
        ]
      }
    }
  },
  methods:{
    submit(){
      let form = document.querySelector('form')
      let formData = new FormData(form)

      let object = {}
      formData.forEach(function(value, key){
          object[key] = value
      })
      var json = JSON.stringify(object)

      console.log(json)
    }
  }
}
</script>

<style>

</style>
