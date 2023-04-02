<template>
  <div class="die" @click="toggle()" :class="[value, disabled ? 'disabled' : '']">
    <svg viewBox="0 0 50 50">
      <path d="M10,10l30,30l-15,-15l15,-15l-30,30" style="fill:none;stroke-width:10px;"/>
    </svg>
  </div>
</template>

<script>
import AbstractDie from "@/components/AbstractDie.vue";

export default {
  name: 'ColourDie',
  extends: AbstractDie,
  data() {
    return {
      possibleValues: [
        'blue',
        'red',
        'green',
        'orange',
        'yellow',
        'black'
      ]
    }
  },
}
</script>

<style scoped>
.blue {
  stroke: #5CC5F0;
}
.red {
  stroke: #E60040;
}
.green {
  stroke: #97C01D;
}
.orange {
  stroke: #F17A02;
}
.yellow {
  stroke: #FFCB09;
}
.black {
  stroke: #000;
}
</style>
