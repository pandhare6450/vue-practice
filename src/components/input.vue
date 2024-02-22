<template>
  <div>
    <input type="text" :value="modelValue" @change="$emit('update:modelValue' , $event.target.value)" >
  </div>
</template>

<script>
  export default {
    name:'Input',
    props: {
      modelValue:String
    }
  }
</script>