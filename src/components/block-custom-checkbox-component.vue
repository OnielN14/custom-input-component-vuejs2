<template lang="html">
  <section>
    <h3>{{blockTitle}}</h3>

    <checkbox v-for="(item,index) in checkboxData.data" :key="index" :nameGroup="checkboxData.name" :values="item.value" :label="item.label" :id="checkboxData.name+index" v-model="selected" :modelValue="selected" @input="updateValue"></checkbox>
  </section>
</template>

<script>
import Checkbox from './custom-input/input-checkbox-component.vue'

export default {
  props:['blockTitle', 'checkboxData'],
  components:{
    Checkbox
  },
  data(){
    return {
      selected : ""
    }
  },
  methods:{
    updateValue(){
      this.$emit('input', this.selected)
    }
  }
}
</script>
