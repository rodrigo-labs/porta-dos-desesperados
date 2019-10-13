<template>
  <div class="door-area">
    <div class="door-frame" :class="{ selected: selected && !open }">
      <Gift v-if="open && hasDift" />
    </div>
    <div class="door" :class="{ open }" @click="selected = !selected">
      <div class="number" :class="{ selected }">{{ number }}</div>
      <div class="knob" :class="{ selected }" @click="open = true"></div>
    </div>
  </div>
</template>

<script>
import Gift from "./Gift";

export default {
  name: "Door",
  components: { Gift },
  props: {
    number: {},
    hasGift: { type: Boolean }
  },
  data() {
    return {
      open: false,
      selected: false
    };
  }
};
</script>

<style>
:root {
  --door-border: 5px solid brown;
  --selected-border: 5px solid yellow;
}

.door-area {
  position: relative;
  width: 14.25rem;
  height: 22.15rem;
  border-bottom: 10px solid #aaa;
  margin-bottom: 1.5rem;
  font-size: 3rem;

  display: flex;
  justify-content: center;
}

.door-frame {
  position: absolute;
  width: 12.85rem;
  height: 21.4rem;

  border-left: var(--door-border);
  border-top: var(--door-border);
  border-right: var(--door-border);

  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.door {
  position: absolute;
  top: 5px;
  width: 12.25rem;
  height: 21.1rem;
  background-color: chocolate;

  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1.2rem;
}

.door .knob {
  width: 1.2rem;
  height: 1.2rem;
  border-radius: 0.6rem;
  background-color: brown;
  align-self: flex-start;
  margin-top: 4.5rem;
}

.door-frame.selected {
  border-left: var(--selected-border);
  border-top: var(--selected-border);
  border-right: var(--selected-border);
}

.door .number.selected {
  color: yellow;
}

.door .knob.selected {
  background-color: yellow;
}

.door.open {
  background-color: #0007;
}

.door.open .knob {
  display: none;
}

.door.open .number {
  display: none;
}
</style>
