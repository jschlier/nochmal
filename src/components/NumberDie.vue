<template>
  <div class="die" @click="toggle()" :class="{'disabled': disabled}">
    <svg viewBox="0 0 50 50">
      <circle v-for="(dot, index) in value.dots" :key="index" :cx="dot.x" :cy="dot.y" r="5"/>
      <text v-if="value.text" x="14px" y="41px" style="font-family:sans-serif;font-size:42px;">
        {{ value.text }}
      </text>
    </svg>
  </div>
</template>

<script>
import AbstractDie from "@/components/AbstractDie.vue";

export default {
  name: 'NumberDie',
  extends: AbstractDie,
  data() {
    return {
      possibleValues: [
        {
          dots: [{x: 25, y: 25}]
        },
        {
          dots: [{x: 10, y: 10}, {x: 40, y: 40}]
        },
        {
          dots: [{x: 10, y: 10}, {x: 25, y: 25}, {x: 40, y: 40}]
        },
        {
          dots: [{x: 10, y: 10}, {x: 10, y: 40}, {x: 40, y: 10}, {x: 40, y: 40}]
        },
        {
          dots: [{x: 10, y: 10}, {x: 10, y: 40}, {x: 25, y: 25}, {x: 40, y: 10}, {x: 40, y: 40}]
        },
        {
          text: '?'
        }
      ]
    }
  }
}
</script>
