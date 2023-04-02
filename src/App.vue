<template>

  <div id="table">

    <component
        v-for="(die, index) in dice" :key="index"
        :is="`${die}-die`"
        ref="dice"
    />

    <button @click="roll()">Würfeln</button>
  </div>

</template>

<script>
import NumberDie from './components/NumberDie.vue'
import ColourDie from './components/ColourDie.vue'

export default {
  name: 'App',
  components: {
    NumberDie,
    ColourDie
  },
  data() {
    return {
      dice: [
        'number',
        'number',
        'number',
        'colour',
        'colour',
        'colour'
      ],
    }
  },
  methods: {
    roll() {
      this.$refs.dice.forEach((die) => {
        die.roll();
      });
    }
  }
}
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#table {
  display: flex;
  align-items: center;
  justify-content: space-around;
  flex-wrap: wrap;
  width: 300px;
  margin: auto;
}

button {
  width: 100%;
  padding: 0.35em 1.2em;
  margin: 2em 25px;
  border: 0.1em solid #000;
  border-radius: 0.12em;
  transition: all 0.2s;
  background-color: #FFF;
}

button:hover {
  background-color: buttonface;
}

@media all and (max-width: 30em) {
  button {
    width: 100%;
  }
}
</style>
