<template>
  <div>
    <h1>Shuffle</h1>
    <template v-for="name in names" :key="name">
      <h4>{{ name }}</h4>
      <input type="text" placeholder="Enter field">
    </template>
    <br />
    <br />
    <button @click="shuffle">Shuffle</button>
  </div>
</template>

<script>

export default {
  data() {
    let names = ['sachin', 'lata', 'amitab', 'narendra']
    return {
      names
    }
  },
  methods: {
    shuffle() {
      for (var i = this.names.length - 1; i > 0; i--) {
        var j = Math.floor(Math.random() * (i + 1));
        console.log(Math.floor(Math.random()* (i + 1)));
        var temp = this.names[i];
        this.names[i] = this.names[j];
        this.names[j] = temp;
      }
      return
    },
  },
}
</script>