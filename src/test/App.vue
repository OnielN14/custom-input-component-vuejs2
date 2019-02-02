<template>
  <div id="app">
    <vue-checkbox
			v-for="(item, index) in checkboxHobby.data"
			:id="checkboxHobby.name+index"
			:key="index"
			:nameGroup="checkboxHobby.name"
			:values="item.value"
			:label="item.label"
			:modelValue = "form.hobby"
			v-model="form.hobby"></vue-checkbox>

			<div>
			<p>Selected : {{form.hobby}}</p>
			</div>
  </div>
</template>

<script>
import {VueRadio,VueRadioBlock,VueCheckbox,VueCheckboxBlock} from '../index.js'

export default {
  name: 'app',
  components: {
    VueRadio,
    VueRadioBlock,
    VueCheckbox,
    VueCheckboxBlock
  },
  data(){
    return {
      form:{
				hobby : ""
			},
			checkboxHobby : {
				name : 'hobby',
				titile : 'Hobby',
				data: [
					{value:"soccer", label: "Soccer"},
					{value:"watching_anime", label: "Watching Anime"},
					{value:"playing_with_cat", label: "Playing with Cat"},
					{value:"read_history_books", label: "Read History Books"},
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
      }
    }
  },
  methods:{
    submit(){
      console.log(this.form);
    }
  }
}
</script>

<style>

</style>
