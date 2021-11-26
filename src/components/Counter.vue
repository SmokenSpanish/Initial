<template>
  <div class="counter__container">
    <button class="btn__counter btn__counter-minus" 
    @click="decreaseCount" 
    type="button">-</button>
    <input class="input__counter" 
    type="number" 
    :value="counter" :min="minCount" :max="maxCount" />
    <button class="btn__counter btn__counter-plus" @click="increaseCount">+</button>
  </div>
</template>

<script>
export default {
  name: "counter",

  data() {
    return {
      counter: 1,
      minCount: 1,
      maxCount: 10
    };
  },

  methods: {
    increaseCount() {
      if(this.counter < this.maxCount) {
        this.counter++
      }
    },

    decreaseCount() {
      if(this.counter > this.minCount) {
        this.counter--
      }
    }
  }
};
</script>

<style>
button {
  padding: 0;
}
.counter__container {
  display: flex;
}

.btn__counter {
  width: 20px;
  height: 20px;
}

.input__counter {
  padding: 0;
  width: 35px;
  height: 20px;
}

</style>