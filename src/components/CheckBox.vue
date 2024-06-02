<template>
  <input type="checkbox" class="input-checkbox" @change="handleChange" />
</template>

<script>
export default {
  name: "CheckBox",
  methods: {
    handleChange(event) {
      this.$emit("change", event.target.checked);
    },
  },
};
</script>

<style scoped></style>
