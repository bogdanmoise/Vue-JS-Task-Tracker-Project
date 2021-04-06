<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>{{ task.text }}
            <i @click="$emit('delete-task', id)" class="fas fa-times"></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>

export default {
    name: "Task",
    props: {
        task: Object
    },
    emits: ['toggle-reminder', 'delete-task']
}

</script>

<style scope>

.fas {
  color: rgb(128, 23, 23);
  margin-top: 15px;
}

.fas:hover {
    color: red;
}

.task {
  background: #f4f4f4;
  margin: 10px 5px;
  padding: 10px 20px;
  cursor: pointer;
  border: 1px solid rgb(90, 89, 89);
}

.task:hover {
background: #219e872c;
}

.task.reminder {
  border-left: 10px solid #219e87;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

</style>