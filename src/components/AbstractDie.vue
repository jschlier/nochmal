<script>
export default {
  abstract: true,
  expose: ['roll', 'toggle'],
  data() {
    return {
      disabled: false,
      value: null,
      possibleValues: {
        type: Array,
        default() {
          return [];
        }
      }
    }
  },
  created() {
    this.value = this.possibleValues[this.possibleValues.length -1];
  },
  methods: {
    roll() {
      this.disabled = false;
      this.value = this.possibleValues[Math.random() * this.possibleValues.length >> 0];
    },
    toggle() {
      this.disabled = !this.disabled;
    },
  }
}
</script>

<style>
.die {
  padding: 4px;
  width: 50px;
  height: 50px;
  border-radius: 10%;
  border: solid 1px black;
  margin: 1em;
}

.die.disabled {
  background-color: lightgrey;
}
</style>
