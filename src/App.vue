<template>
  <div id="app">
    <h1>Porta dos Deseperados</h1>
    <!-- <h3>glu glu - yeah yeah</h3> -->
    <div class="form">
      <div v-if="!started">
        <label for="portsAmount">Quantas portas?</label>
        <input type="text" id="portsAmount" size="3" v-model.number="portsAmount" />
      </div>

      <div v-if="!started">
        <label for="selectedPort">Qual porta é a premiada?</label>
        <input type="text" id="selectedPort" size="3" v-model.number="selectedPort" />
      </div>
      <button v-if="!started" @click="started = true">Iniciar</button>
      <button v-if="started" @click="started = false">Reiniciar</button>
    </div>

    <div class="doors" v-if="started">
      <div v-for="door in portsAmount" :key="door">
        <Door :hasGift="door === selectedPort" :number="door" />
      </div>
    </div>
  </div>
</template>

<script>
import Door from "./components/Door";

export default {
  name: "App",
  components: { Door },
  data() {
    return {
      started: false,
      portsAmount: 3,
      selectedPort: null
    };
  }
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

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 3rem;
}

.form,
.form input,
.form button {
  margin-bottom: 0.75rem;
  font-size: 2rem;
}

.doors {
  align-self: stretch;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>
