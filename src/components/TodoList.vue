<template>
<h3></h3>
 <!--  <ul>
    <li
      v-for="(todolist, index) in TodoLists"
      :key="index"
    >
    
      <span class="name">{{todolist.name}}  <input type="checkbox" @click="checkbox"/></span>
      

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
 -->



</template>

<script>
export default {
  props: {
    TodoLists: Array,
    DoneLists:Array,
    done:Boolean,
  },
  methods : {
/*     checkbox() {
       var done = true;
      if (done == true) {
        console.log="true";
        this.TodoLists.push(this.DoneLists[0])
        this.TodoLists.shift();
      }
    } */
  }
  

}
</script>

<style scoped> 

</style>