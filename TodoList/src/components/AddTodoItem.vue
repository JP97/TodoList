<template>
    <div class="addTodoItem">
        <div>
            <input type="text" value="Write your task here"/>
            <button @click="$emit('add-todoitem', input.value)">Add task</button>
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style scoped>
    .addTodoItem{
        background-color: greenyellow;
        padding:20px;
        border: 2px solid grey;
    }
</style>