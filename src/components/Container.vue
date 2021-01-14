<template>
  <div class="container">
    <input
      type="text"
      v-model="msg"
    >
    <button @click="Create">+</button>
    <TodoList
      :TodoLists="TodoLists"
      :DoneLists="DoneLists"
      :done=false
    />
   
  <h3>tareas pendientes</h3>
  <ul>
    <li
      v-for="(todolist, index) in TodoLists"
      :key="index"
    >
    
      <span class="name">{{todolist.name}}  <input type="checkbox" id="checkbox" @click="checkbox"/></span>
      

    </li>
  </ul>

  <h3>Tareas Terminadas</h3>
  <ul>
    <li
      v-for="(donelist, index) in DoneLists"
      :key="index"
    >
    
      <span class="name">{{donelist.name}}  <input  type="checkbox" id="checkbox" @click='checkbox'/></span>
      

    </li>
  </ul>


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
      { id: 3, name: 'agregar checkbox'},
    ];
        let exampleDataDone = [
      { id: 1, name: 'Tarea Hecha'},
    ];
    return {
      TodoLists: ref(exampleData),
      DoneLists: ref(exampleDataDone),
    };
  },
  methods: {
    Create() {
      let id = 4;
      id += 1;
      var done = false;
      const next = { id, name: this.msg,done};
      this.TodoLists.push(next);
    },
        checkbox() {
       var done = true;
      if (done === true) {
       this.DoneLists.push(this.TodoLists[0])
      } else {
        this.TodoLists.push(this.DoneLists[0])
      }
    }

    }
  }
  
</script>