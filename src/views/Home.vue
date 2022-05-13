<template>
  <section class="home">
    <h1 class="fw-bold mt-3 text-center text-white">Todo List</h1>
    <div class="container shadow-5-strong bg-white bg-opacity-50 py-1">
      <div class="text-center">
        <div class="my-3 mx-2">
          <input type="text" v-model="todo" placeholder="Add todo..." />
          <button @click="addTodo()" class="btn btn-primary rounded mx-2">
            Add <i class="fa-solid fa-plus"></i>
          </button>
        </div>
      </div>
      <div class="border">
        <div v-for="todo in todos" v-bind:key="todo.id" class="my-3">
          <div class="flex flex-row justify-center mx-2">
            <h4 class="text-white">
              {{ todo.data }}
            </h4>
            <div class="">
              <button class="btn btn-success" @click="removeTodo(todo.id)">
                <i class="fa-solid fa-check"></i>
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="mb-3 mx-3">
        <button @click="clearAllTodos" class="btn margin btn-danger rounded">
          Clear <i class="fa-solid fa-xmark"></i>
        </button>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      todo: "",
      todos: [
        {
          id: Math.random() * 10000,
          data: "This is my Todo List",
        },
        {
          id: Math.random() * 10000,
          data: "What I have to do",
        },
      ],
    };
  },
  methods: {
    addTodo() {
      if (this.todo.length === 0) {
        alert("Don't you have something todo?");
      } else {
        this.todos.push({
          id: Math.random() * 10000,
          data: this.todo,
        });
        this.todo = "";
      }
    },
    removeTodo(todoId) {
      this.todos = this.todos.filter((todo) => todo.id !== todoId);
    },
    clearAllTodos() {
      this.todos = [];
    },
  },
};
</script>

<style>
.home {
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100vh;
  position: fixed;
  background: linear-gradient(
      rgba(255, 255, 255, 0.1),
      rgba(255, 255, 255, 0.1)
    ),
    url("https://images.unsplash.com/photo-1586202690180-1967f682ef1a?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1488&q=80");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.border {
  margin: 20px;
}

.margin {
  margin: 20px;
}
</style>
