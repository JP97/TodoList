<template>
    <div class="TodoItem">
        <div v-for="todo in todos">
            <h1>{{todos.name}}</h1>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TodoItem",
        props: ["todos"]
    }
</script>

<style scoped>
</style>