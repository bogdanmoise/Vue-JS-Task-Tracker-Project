<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @btn-click="$emit('toggle-add-task')"
         :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'rgb(128, 23, 23)' : '#219e87'"/>
    </header>
</template>

<script>

import Button from "./Button"

export default {
    name: "Header",
    components: {
         Button
    },
    props: {
        title: String,
        showAddTask: Boolean
    },
    emits: ['toggle-add-task']
}
</script>

<style scoped>

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

h1 {
    color: rgb(36, 63, 85);
}

</style>