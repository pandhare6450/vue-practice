<template>
  <div>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>
    {{ state }}  {{ likes }}
  <input type="text" v-model="movie" v-bind="$attrs">
  <input type="text" v-model="movieInfo.title">
  <input type="text" v-model="movieInfo.actor">
  </div>
</template>

<script>
export default {
  name: 'volumeTracker',
  props:{
    state:{
      type:String,
      requierd:true,
      default:'Not'
    },
    likes:Number
  },
  data() {
    return {
      volume: 0,
      movie: 'K#g',
      movieInfo:{
        title:'',
        actor:'',
      }
    }
  },
  watch: {
    volume(newVolume, prevVolume) {
      if (newVolume > prevVolume && newVolume == 16) {
        alert('Higher volume may damage ear..')
      }
    },
    movie:{
      handler(newMovie){
        console.log('Make api call to' + newMovie);
      },
      immediate:true
    },
    movieInfo: {
      handler(newMovie){
        console.log({newMovie});
      },
      deep:true
    }
  },
  inheritAttrs:false,
}
</script>