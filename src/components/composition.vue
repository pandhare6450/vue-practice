<template>
  <div>
    Composition API
    <input type="text" v-model="myName" ref="inputRef">
    {{ myName }}

    <input type="text" v-model="name" >
    <br>
    <br>
    <input type="text" v-model.lazy="surname" >
    <br>
    <br>
    <input type="text" v-model="profile" >
    <br>
    <br>
    {{ fullName}}
  </div>
</template>

<script>
import { ref, reactive, toRefs,computed, watch, onMounted } from 'vue'
  export default {
    name:'Composition',
    setup(){
      const inputRef  = ref(null)
      const myName = ref('')
      const form = reactive({
        name:'hello world',
        surname:'Dear',
        profile:'TIger',
      })
      onMounted(()=>{
        inputRef.value.focus()
      })
      const fullName = computed(function(){
        return form.name + ' ' + form.surname
      })
      watch(myName, (newVal, oldVal) =>{
        console.log({newVal, oldVal});
      },
       {deep:true,immediate:true}
      )
      return{
        myName,
        ...toRefs(form),
        fullName,
        inputRef
      }
    }
  }
</script>