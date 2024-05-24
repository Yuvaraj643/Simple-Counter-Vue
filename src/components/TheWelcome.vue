<template>
  <div class="main-section">
    <header>
      <h1>Simple Counter App</h1>
    </header>

    <p class="count">{{ counterStore.count }}</p>
    <div class="counter">
      <button @click="counterStore.decrement">Decrement</button>

      <button @click="counterStore.reset">Reset</button>
      <button @click="counterStore.increment">Increment</button>
    </div>
  </div>
</template>

<script>
import { useCounterStore } from "@/stores/counter";
export default {
  setup() {
    const counterStore = useCounterStore();

    return {
      counterStore,
    };
  },
  data() {
    return {
      count: 0,
    };
  },
  methods: {},
};
</script>

<style scoped>
.main-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px;
}

.count {
  font-size: 40px;
  font-weight: bold;
}

.counter {
  display: flex;
  gap: 30px;
}

.counter button {
  font-size: 15px;
  padding: 15px 20px;
  border-radius: 15px;
}
</style>
