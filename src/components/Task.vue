<template>
    <div
      @dblclick="$emit('toggle-reminder', task.id)"
      :class="[task.reminder ? 'reminder' : '', 'task']"
    >
      <h3>
        {{ task.text }}
        <i class="fas fa-times"></i>
      </h3>
      <p>{{ task.day }}</p>
      <div @click="$emit('edit-task', task.id)">
        edit
      </div>
      <div @click="$emit('delete-task', task.id)">
        delete
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'TaskComponent',
    props: {
      task: Object,
    },
  }
  </script>
  
  <style scope>
  .fas {
    color: red;
  }
  
  .task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
  }
  
  .task.reminder {
    border-left: 5px solid green;
  }
  
  .task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  </style>
  