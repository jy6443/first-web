<template>
  <div>
    <InputTodo @add="addMessage" />
    <hr />
    <ul class="list-group">
      <li
        v-for="(item, index) in list"
        :key="index"
        class="list-group-item d-flex justify-content-between align-items-center"
      >
        <span :class="{ completed: item.completed }">{{ item.text }}</span>
        <CheckBox @change="(checked) => toggleComplete(index, checked)" />
      </li>
    </ul>
  </div>
</template>

<script>
import CheckBox from "./CheckBox.vue";
import InputTodo from "./InputTodo.vue";
export default {
  name: "ListItem",
  components: { CheckBox, InputTodo },
  data() {
    return {
      list: [
        { text: "저녁에 라면먹기", completed: false },
        { text: "면접 준비하기", completed: false },
        { text: "집가면서 아이스크림 사먹기", completed: false },
      ],
    };
  },
  methods: {
    addMessage(msg) {
      this.list.push({ text: msg, completed: false });
    },
    toggleComplete(index, checked) {
      this.$set(this.list, index, { ...this.list[index], completed: checked });
    },
  },
};
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>
