<template>
  <div>
    All componenets Here
    <!-- <shuffle/> -->
    <!-- <volumeTracker state="render" :likes="50" id="myData"/> -->
    <!-- <provide/> -->
    <Input v-model="name"/>
    <!-- <div>
      <br>
      <button @click="activeTab = 'TabA'">Tab A</button>&nbsp;
      <button @click="activeTab = 'TabB'">Tab B</button>&nbsp;
      <button @click="activeTab = 'TabC'">Tab C</button>&nbsp;
    </div>
    <keep-alive>
    <component :is="activeTab" />
    </keep-alive>
    {{ name }} -->

    <Composition/>
  </div>
</template>

<script>
import shuffle from './components/shuffle.vue'
import volumeTracker from './components/watch.vue'
import provide from './components/provide.vue'
import Input from './components/input.vue'
import TabA from './components/Tab_A.vue'
import TabB from './components/Tab_B.vue'
import TabC from './components/Tab_C.vue'
import Composition from './components/Composition.vue'
export default {
  name: "App",
  components: {
    shuffle, volumeTracker, provide, Input,
    TabA, TabB, TabC,Composition
  },
  data() {
    const activeTab = 'TabA'
    return {
      name: 'arther',
      activeTab
    }
  },
  provide: {
    user: 'Emailsadasd'
  }
}
</script>

<style scoped>
.added {
  color: green
}

.delete {
  color: rgb(123, 5, 5)
}
</style>
