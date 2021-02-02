<template>
  <h3>
    Declarative rendering
  </h3>
  <p>MY COUNTER:: {{ counter }}</p>
  <button @click="startTimer">{{ getBtnLable }}</button>
</template>

<script>
export default {
  name: 'DeclarativeRendering',
  data() {
    return {
      counter: 0,
      isTimerStarted: false,
    };
  },

  // don't change any properties that in data (ex: value of counter and isTimerStarted, it will result to side effect which is not a proper place )
  computed: {
    getBtnLable() {
      return this.isTimerStarted === false
        ? 'CLICK TO START TIMER'
        : 'STOP TIMER';
    },
  },
  methods: {
    startTimer() {
      console.log(this.isTimerStarted);
      this.isTimerStarted = !this.isTimerStarted;
      const interval = setInterval(() => {
        this.counter++;

        if (!this.isTimerStarted) {
          clearInterval(interval);
        }
      }, 1000);
    },
  },
};
</script>

<style scoped>
button {
  background-color: beige;
  border-radius: 4px;
  max-width: 300px;
  height: 40px;
  text-transform: uppercase;
  color: black;
  transition: 0.26s ease;
}

button:hover {
  cursor: pointer;
  transform: scale(1.05);
}

button:active {
  background-color: black;
}
</style>
