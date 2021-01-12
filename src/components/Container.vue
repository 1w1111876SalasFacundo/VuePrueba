<template>
  <div class="container">
    <input
      type="text"
      v-model="msg"
    >
    <button @click="Create">+</button>
    <TodoList
      :TodoLists="TodoLists"
      :Delete="Delete"
    />
  </div>
</template>

<script>
import TodoList from './TodoList';
import { ref } from "@vue/runtime-core";
export default {
  components: {
    TodoList,
  },
  setup() {
    let exampleData = [
      { id: 1, name: 'Intentado hacer funcion enviar' },
      { id: 2, name: 'Cenar' },
      { id: 3, name: 'agregar checkbox' },
    ];
    return {
      TodoLists: ref(exampleData)
    };
  },
  methods: {
    Create() {
      let id = 4;
      id += 1;
      const next = { id, name: this.msg };
      this.TodoLists.push(next);
    }

  }
}
</script>