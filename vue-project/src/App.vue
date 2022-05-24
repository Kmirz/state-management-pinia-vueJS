<script >
import * as bootstrap from "bootstrap";
import { useCounterStore } from "./stores/counter";
import { storeToRefs } from "pinia";

export default {
  name: "app",
  setup() {
    const main = useCounterStore();
    console.log(main);
    const { counter, name } = storeToRefs(main);

    return { counter, main, name };
  },
};
</script>

<template>
  <div class="wrapper">
    <div class="counterView">Hello {{ name }}! Your value is {{ counter }}</div>
    <button class="btn btn-primary" @click="main.increment">Add Value</button>
    <label for="textbox1"> Name: </label>
    <form action="">
      <input type="text" v-model="name" name="textbox" id="textbox1" />
    </form>
  </div>
</template>

<style>
* {
  padding: 1em;
}

.wrapper {
  display: flex;
  align-items: center;
}
</style>
