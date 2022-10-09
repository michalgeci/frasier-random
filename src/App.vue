<template>
  <div>
    <h1>{{code}}</h1>
    <h3>{{title}}</h3>
    <p>{{description}}</p>
  </div>

  <button @click="setEpisode">Náhodná epizóda</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import episodes from './data/episodes.json'

function getRandomInt(max) {
  return Math.floor(Math.random() * max);
}

export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // },
  data() {
    return {
      code: "",
      title: "",
      description: ""
    }
  },
  methods: {
    setEpisode() {
      let n = getRandomInt(episodes.length)
      this.code = episodes[n].code
      this.title = episodes[n].title
      this.description = episodes[n].description
    }
  },
  mounted() {
    this.setEpisode()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 90%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}
html, body {
  height: 100%;
}
button {
  border-radius: 8px;
  padding: 12px 28px;
  font-size: 16px;
  border: none;
  background-color: #008CBA;
  color: white;
}
p {
  margin-left: 12px;
  margin-right: 12px;
}
</style>
