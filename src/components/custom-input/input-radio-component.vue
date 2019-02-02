<template lang="html">
  <div class="">
    <input :id="id" type="radio" :name="nameGroup" :value="values" @input="updateParentValue()" ref="refsElement">
    <label :for="id">{{label}}</label>
  </div>
</template>

<script>
export default {
  props: ['id','nameGroup','values','label'],
  methods:{
    updateParentValue(){
      this.$emit('input', this.$refs.refsElement.value)
    }
  }
}
</script>
