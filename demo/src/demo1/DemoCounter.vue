<template>
  <demo-container>
    <div class="counter">
      <counter-button @action="decrement">-</counter-button>
      <counter-value :value="count" />
      <counter-button @action="increment">+</counter-button>
    </div>
  </demo-container>
</template>

<script setup>
import { ref } from "vue";
import CounterValue from "./CounterValue.vue";
import CounterButton from "./CounterButton.vue";
import DemoContainer from '../components/DemoContainer.vue';

const count = ref(0);

const decrement = () => {
  count.value--;
};

const increment = () => {
  count.value++;
};
</script>

<style lang="scss" scoped>
.counter {
  display: flex;
  align-items: center;
}
</style>
