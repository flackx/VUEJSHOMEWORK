<template>
  <button :class="{ active: isActive }" @click="handleClick">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    isActive: {
      type: Boolean,
      required: true,
    },
  },
  methods: {
    handleClick() {
      this.$emit('click');
    },
  },
};
</script>

<style scoped>
.active {
  background-color: #4CAF50;
}
</style>
