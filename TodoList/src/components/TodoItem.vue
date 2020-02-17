<template>
    <!-- den binder "is-finished" klassen til Todoitem når todoitem.done er truthy (kinda if statement) -->
    <!-- vi binder en class (v-bind:class) på den condition at "todoitem.done" er true-->
    <div class="TodoItem" v-bind:class="{'is-finished':todoitem.completed}">
        <!-- bruger props for at vise de data -->
        <p>
            <!-- er sådan set et event. Ved ændring af checkboxes kører vi denne methode -->
        <input type="checkbox" v-on:change="markCompleted"/>
        {{todoitem.name}}
            <!-- click event der emitter det "del-todo" event der sender todoitem.id med som parameter -->
        <button @click="$emit('del-todoitem', todoitem.id)" class="del">DELETE</button>
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

        //alle methoder bliver skrevet her.
        //man kan tilgå props med hjælp af "this." som man kan se forneden
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

    .del{
        color:red;
    }
</style>