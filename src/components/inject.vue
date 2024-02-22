<template>
  <div>
    <h3>I am from Inject</h3>
    {{ email }}
  <button @click="$emit('close','Manoj')">Hide Me</button>
  </div>
</template>

<script>
import { inject } from 'vue';

export default {
  inject:['user'],
  emits:['close'],
  setup(){
    const email = inject('email');
    return {
      email
    }
  }

}
</script>
