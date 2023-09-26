<script setup>
import { ref } from 'vue';

const tasks = ref([
  { text: "Study", completed: false },
  { text: "Paint house", completed: false },
  { text: "Grocery shopping", completed: false },
  { text: "Time at hairdresser", completed: false }
]);

const newTask = ref('');

function addNewTask() {
  if (newTask.value.trim() === "") return;
  tasks.value.push({ text: newTask.value, completed: false });
  newTask.value = '';
}

function removeTask(task) {
 tasks.value = tasks.value.filter((remove) => remove !== task)
}
</script>

<template>
  <div id="container">
  <div id="task-list">
    <ul>
      <li v-for="task in tasks" :key="task.text" :class="{ 'completed': task.completed }">
        <input type="checkbox" v-model="task.completed" />
        {{ task.text }}
        <button id="remove-button" @click="removeTask(task)">Delete</button>
      </li>
    </ul>
    </div>
    <div id="add-new-task"> 
    <textarea v-model="newTask" placeholder="Add new task"></textarea>
    <button id="add-button" @click="addNewTask">Add</button>
    </div>
  </div>
</template>

<style scoped>
#container{
    display: flex;
    flex-direction: column;
    align-items: center;
}
ul{
    border: 1.5px solid;
    padding:25px;
}
li{
    list-style: none;
    padding-bottom: 5px;
}
.completed {
  text-decoration: line-through;
}
#add-new-task{
    display: flex;
    align-items: center;
}
button{
    margin-left: 5px;
    background-color: #9F1E49;
    color:white;
    padding: 5px 8px;
    border: none;
    border-radius: 12px;
    cursor: pointer;
}
textarea{
    border-color: #2F1B41;
    font-size: 1em;
}

</style>
