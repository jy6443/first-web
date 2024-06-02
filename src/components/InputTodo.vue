<template>
  <div>
    <input type="text" v-model="text" />
    <button @click="insert">추가</button>
  </div>
</template>

<script>
export default {
  name: "InputTodo",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    insert() {
      this.$emit("add", this.text);
      console.log(this.text);
    },
  },
};
</script>

<style scoped></style>
