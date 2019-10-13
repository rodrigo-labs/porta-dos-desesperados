<template>
  <div class="gift">
    <div class="gift-tie-1"></div>
    <div class="gift-tie-2"></div>
    <div class="gift-top"></div>
    <div class="gift-body"></div>
  </div>
</template>

<script>
export default {
  name: "Gift"
};
</script>

<style>
.gift {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 10;
}

.gift-top {
  width: 6.5rem;
  height: 2rem;
  background-color: #7aa944;
}

.gift-body {
  width: 6rem;
  height: 4rem;
  background-color: #5c7e32;
}

.gift-tie-1 {
  position: absolute;
  width: 1rem;
  height: 6rem;
  background-color: red;
}

.gift-tie-2 {
  position: absolute;
  top: 2.75rem;
  width: 6rem;
  height: 1rem;
  background-color: red;
}
</style>
