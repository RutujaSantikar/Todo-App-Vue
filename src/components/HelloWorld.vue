<template>
  <div class="body">
    <div class="left-cont image-container">
      <img v-bind:src="todoImage" />
    </div>
    <div class="right-cont text-container">
      <h2>Have a plans for Today ?</h2>
      <h5>List it Here</h5>

      <div class="btn-cont">
        <button class="createtodo" @click="isCard = !isCard">
          Create todo
        </button>
      </div>

      <todo-app v-show="!isCard"></todo-app>
    </div>
  </div>
</template>

<script>
import TodoApp from "./TodoApp.vue";
export default {
  components: {
    TodoApp,
  },
  name: "HelloWorld",
  data() {
    return {
      isCard: true,

      todoImage: require("../assets/todo-logo.png"),
    };
  },
  methods: {},
};
</script>

<style scoped>
.body {
  width: 85%;
  margin: 2em auto;
  display: flex;
  justify-content: space-between;
}
.right-cont {
  background-color: #fbcf02;
  border-radius: 41% 59% 24% 76% / 71% 37% 63% 29%;
  width: 44%;
}
h2 {
  letter-spacing: 0.1em;
  color: #6666ff;
}
h5 {
  letter-spacing: 0.1em;
  color: #252468;
}
.createtodo {
  border: none;
  padding: 1em;
  border-radius: 5em;
  background-color: #d63384;
  color: white;
  float: right;
  letter-spacing: 0.1em;
  margin-top: 1em;
}


</style>
