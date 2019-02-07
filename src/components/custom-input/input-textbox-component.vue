<template>
  <div class="">
    <label :for="id" v-if="showLabel">{{label}}</label>
    <input :id="id" type="text" :name="nameGroup" :value="values"  @input="updateParentValue()" ref="refsElement">
  </div>
</template>

<script>
export default {
  props: {
    id:{
      type:String,
      required:true
    },
    values:{
      required:false
    },
    label:{
      type:String,
    },
    nameGroup:{
      type:String,
      required:true
    },
    showLabel:{
      default:false
    }
  },
  methods:{
    updateParentValue(){
      this.$emit('input', this.$refs.refsElement.value)
    }
  }
}
</script>
