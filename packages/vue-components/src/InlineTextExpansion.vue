<template>
  <div class="expansion">
    <button @click="isExpanded = !isExpanded" class="expansion-button">
      {{ header }}
      <div v-if="!isExpanded" class="arrow">&#187;</div>
      <div v-else class="arrow">&#171;</div>
    </button>
    <div v-if="isExpanded" class="expansion-text">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    header: {
      type: String,
      default: 'Click to reveal!',
    },
  },
  data() {
    return {
      isExpanded: false,
    };
  },
};
</script>

<style>
.arrow {
  color: grey;
  display: inline-block;
}

.expansion {
  display: inline-block;
}

.expansion-button {
  border: 1px solid #ddd;
  border-radius: 3px;
  cursor: pointer;
  display: inline-block;
  margin: 0 2px 0;
}

.expansion-text {
  background-color: #FDFD96;
  border-radius: 4px;
  display: inline-block;
}
</style>
