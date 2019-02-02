<template lang="html">
  <section>
    <h3>{{blockTitle}}</h3>

    <radio v-for="(item,index) in radioData.data" :key="index" :nameGroup="radioData.name" :values="item.value" :text="item.text" :id="radioData.name+index" v-model="selected" @input="updateValue"></radio>

  </section>
</template>

<script>
import Radio from './custom-input/input-radio-component.vue'

export default {
  props:['blockTitle', 'radioData'],
  components:{
    Radio
  },
  data(){
    return {
      selected : ''
    }
  },
  methods:{
    updateValue(){
      this.$emit('input', this.selected)
    }
  }
}
</script>
