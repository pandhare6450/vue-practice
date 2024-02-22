<template>
  <div>
    <h2>I am from provide</h2>
    <input type="text" v-model="email">
    {{  email }}

    <inject v-show="isShow" @close="closePopup"/>
    <br>
    <br>
    <button @click="isShow=!isShow">Show</button>
  </div>
</template>

<script>
import { ref, provide } from 'vue';
import inject from './inject.vue'
export default {
  components:{
    inject
  },
  data () {
    const email = ref('')
    provide('email', email)
    return {
      email,
      isShow:false
    }
  },
  methods:{
    closePopup(name){
      this.isShow = false;
      console.log({name});
    }
  }
}
</script>
