<template>
  <div class="todo-card">
    <div class="todo-container">
      <input
        type="text"
        id="todoInput"
        class="todo-input"
        v-model="todolist.name"
        @keyup.enter="newTodo"
      /><span
        ><button type="submit" class="addTodoBtn" @click="newTodo">
          Add
        </button></span
      >
    </div>
    <ul>
      <li v-for="todo in todolist" :key="todo.id">
        {{ todo.name
        }}<button class="deleteTodoBtn" @click="deleteTodo(todo)">
          <i class="fas fa-trash-alt">{{ todo.delete }}</i>
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoApp",
  data() {
    return {
      todolist: [],
    };
  },
  methods: {
    newTodo: function () {
      if (!this.todolist.name) {
        return;
      }
      this.todolist.push({
        name: this.todolist.name,
        delete: "",
      });
      this.todolist.name = "";
    },
    deleteTodo: function (todo) {
      this.todolist.splice(this.todolist.indexOf(todo), 1);
    },
  },
};
</script>

<style scoped>
.todo-card {
  width: 70%;
  border: 1px solid lightgrey;
  padding: 1.5em;
  border-radius: 0.4em;
  margin-top: 3em;
  background-color: rgba(255, 255, 255, 0.2);
}
.todo-container {
  width: 100%;
}
#todoInput {
  outline: none;
  padding: 0.6em;
  width: 70%;
  border: 1px solid lightgrey;
  border-radius: 0.4em;
}
.deleteTodoBtn {
  float: right;
  border: none;
  background: none;
}
.fas {
  /* float: right; */
  color: #6666ff;
  line-height: 1.5em;
}
.addTodoBtn {
  outline: none;
  padding: 0.6em;
  width: 20%;
  margin-left: 0.5em;
  border: 1px solid lightgrey;
  border-radius: 0.4em;
  background-color: #252468;
  color: white;
  letter-spacing: 0.1em;
}
ul {
  margin: 0;
  padding: 0;
}
li {
  list-style-type: none;
  background-color: #dae9ff;
  margin-top: 1em;
  padding: 0.5em;
  border-radius: 0.5em;
  color: #252468;
  letter-spacing: 0.1em;
}
</style>
