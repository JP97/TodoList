<template>
    <!-- den binder "is-finished" klassen til Todoitem når todoitem.done er truthy (kinda if statement) -->
    <!-- vi binder en class (v-bind:class) på den condition at "todoitem.done" er true-->
    <div class="TodoItem" v-bind:class="{'is-finished':todoitem.completed}">
        <!-- bruger props for at vise de data -->
        <p>
        <input type="checkbox" v-on:change="markCompleted"/>
        {{todoitem.name}}
        </p>
    </div>
</template>

<script>
    export default {
        //navn af det component
        name: "TodoItem",

        //modtager det array der kommer fra TodosList
        //det er navnet fra de enkelte todoitem fra forloopet i todoslist
        props: ["todoitem"],

        methods: {
            markCompleted() {
                this.todoitem.completed = !this.todoitem.completed;
            }
        }
    }
</script>

<style scoped>
    .TodoItem{
        border: 2px solid grey;
        padding:10px;
        background-color: lightblue;
    }

        /*making an extra class that shows if an todoitem is finished with an extra style*/
    .is-finished{
        text-decoration:line-through
    }

    .checkBox{
        /*lav at checkboxen altid er til venstre*/
        
    }
</style>