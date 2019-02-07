<template>
  <div id="app">
      <!-- <vue-textbox v-model="value" name-group="test" id="test1" :values="selected">
      </vue-textbox>
      
      <vue-radio v-model="selected" v-for="(item, index) in dataRadio.data" :key="index" :id="dataRadio.name + index" :label="item.label" :values="item.value" :name-group="dataRadio.name">

      </vue-radio>

			<div>
			<p>In the TextBox : {{value}}</p>
			<p>Selected from Radio : {{selected}}</p>
			</div> -->

      <div>
        <vue-textbox v-for="(item,index) in dataTextbox" :key="index" :name-group="item.name" :show-label="item.showLabel" :label="item.label" v-model="availableTextbox[index]" :id="item.name+index">

        </vue-textbox>
      </div>
      <div>
        <p v-for="(item,index) in availableTextbox" :key="index">{{item}}</p>
      </div>
  </div>
</template>

<script>
import {VueRadio,VueRadioBlock,VueCheckbox,VueCheckboxBlock,VueTextbox} from '../index.js'

export default {
  name: 'app',
  components: {
    VueRadio,
    VueRadioBlock,
    VueCheckbox,
    VueCheckboxBlock,
    VueTextbox
  },
  data(){
    return {
      availableTextbox:[],
      value:'',
      selected:'',
      dataRadio:{
        name:'radio',
        data:[
          {value:1, label:'Satu'},
          {value:2, label:'Dua'},
          {value:3, label:'Tiga'},
          {value:4, label:'Empat'},
        ]
      },
      dataTextbox:[
        {name:'firstname',label:'Firstname', showLabel:true},
        {name:'lastname',label:'Lasstname', showLabel:true},
        {name:'phonenumber',label:'Phone Number', showLabel:true},
        {name:'email',label:'Email', showLabel:true},
      ]
    }
  },
  methods:{
    submit(){
      console.log(this.form);
    }
  },
  watch:{
    selected(newValue){
      this.value = newValue
    }
  }
}
</script>

<style>

</style>
