<template lang="html">
  <div class="">
    <input :id="id" type="checkbox" :name="nameGroup" :value="values" @input="updateParentValue()" ref="refsElement">
    <label :for="id">{{label}}</label>
  </div>
</template>

<script>
export default {
  model:{
    prop:'modelValue',
    event:'input'
  },
  props: {
    id:{
      type:String,
      required:true
    },
    values:{
      required:true
    },
    label:{
      type:String,
      required:true
    },
    nameGroup:{
      type:String,
      required:true
    },
    modelValue:{
      default:false
    }
  },
  methods:{
    updateParentValue(){
      let isChecked = this.$refs.refsElement.checked

      if (this.modelValue instanceof Array) {
        let newValue = [...this.modelValue]

        if (isChecked) {
          newValue.push(this.values)
        }
        else{
          newValue.splice(newValue.indexOf(this.values), 1)
        }

        this.$emit('input', newValue)
      }
      else{
        this.$emit('input',[this.values])
      }
    }
  }
}
</script>
