<template>
    <div class="TodoItem">
        <!-- bruger props for at vise de data -->
        <p>{{todoitem.name}}</p>
    </div>
</template>

<script>
    export default {
        //navn af det component
        name: "TodoItem",

        //modtager det array der kommer fra TodosList
        //det er navnet fra de enkelte todoitem fra forloopet i todoslist
        props:["todoitem"]
    }
</script>

<style scoped>
</style>