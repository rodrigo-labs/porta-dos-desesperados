<template>
  <div id="app">
    <h1>Porta dos Deseperados</h1>
    <!-- <h3>glu glu - yeah yeah</h3> -->
    <Door number="1" :hasGift="false" />
  </div>
</template>

<script>
import Door from "./components/Door";

export default {
  name: "App",
  components: { Door }
};
</script>

<style>
* {
  box-sizing: border-box;
  font-family: "Montserrat", sans-serif;
}

body {
  color: #fff;
  background: linear-gradient(to right, #22c1c3, #fdbb2d);
}

#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}

#app h1 {
  border: 1px solid #000;
  background-color: #0004;
  padding: 1.25rem;
  margin-bottom: 4rem;
}
</style>
