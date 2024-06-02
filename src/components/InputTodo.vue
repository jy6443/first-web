<template>
  <div>
    <input type="text" v-model="text" placeholder="할일을 추가하십시오." />
    <button @click="insert" class="btn btn-warning">추가</button>
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
    },
  },
};
</script>

<style scoped>
.button {
  margin: auto;
}
</style>
