<template>
  <div>
    <InputTodo @add="addMessage" />
    <hr />
    <ul v-for="(item, index) in list" :key="item.index">
      <li>
        <span>{{ item }} <CheckBox /></span>
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
      list: ["저녁에 라면먹기", "면접 준비하기", "집가면서 아이스크림 사먹기"],
    };
  },
  methods: {
    addMessage(msg) {
      this.list.push(msg);
    },
  },
};
</script>

<style scoped></style>
