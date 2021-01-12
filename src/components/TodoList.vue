<template>
<h3>tareas pendientes</h3>
  <ul>
    <li
      v-for="(todolist, index) in TodoLists"
      :key="index"
    >
    
      <span class="name">{{todolist.name}}  <input type="checkbox" id="task-checkbox"/></span>
      

    </li>
  </ul>
</template>

<script>
export default {
  props: {
    TodoLists: Array,
  }

}
</script>

<style scoped> 

</style>