<template>
  <span>
    <button @click="isExpanded = !isExpanded" class="expansion-button">
      {{ header }}
      <span v-if="!isExpanded" class="arrow">&#187;</span>
      <span v-else class="arrow">&#171;</span>
    </button>
    <span v-if="isExpanded" class="expanded-text">
      <slot></slot>
    </span>
  </span>
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
}

.expanded-text {
  background-color: #FDFD96;
  border-radius: 4px;
}

.expansion-button {
  border: 1px solid #ddd;
  border-radius: 3px;
  cursor: pointer;
  margin: 0 2px 0;
}
</style>
