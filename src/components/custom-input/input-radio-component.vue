<template lang="html">
  <div class="">
    <input :id="id" type="radio" :name="nameGroup" :value="values" :checked="isChecked" @input="updateParentValue()" ref="refsElement">
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
      this.$emit('input', this.$refs.refsElement.value)
    }
  },
  computed:{
    isChecked(){
      if(this.values == this.modelValue){
        return true
      }
      return false
    }
  }
}
</script>
