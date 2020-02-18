<template>
    <div class="addTodoItem">
        <!-- prevent stops the reload from the page and shows the event in the devtools and dont messes with the added todoitem-->
        <form @submit.prevent="addTodoItem">
            <!-- laver two way modelbinding med v-model.lazy der binder til det object todoItemName -->
            <input v-model.lazy="todoItemName" type="text" placeholder="Add new task"/>
            <!-- kunne også havde været <input type="submit"/> ville være bedre da man så kan bruge formen -->
            <!-- kalder direkte til en function da det så overholder singleresponsibility -->
            <input type="submit" value="submit" />
        </form>
    </div>
</template>

<script>
//har downloadet uuid med at skrive npm i uuid i kommandozeile
//er for id
import uuid from 'uuid';

    export default {
        name: 'AddTodoItem',
        data() {
            return {
                todoItemName: '',
                //completed: false
            }
        },
        methods: {
            addTodoItem() {
                // construct the todoitem before emitting to app component
                const newTodoItem = {
                    id: uuid.v4(),
                    name: this.todoItemName,
                    completed: false
                }
                this.$emit('add-Todoitem', newTodoItem);
            }
        }
    }
</script>

<style scoped>
    .addTodoItem{
        background-color: greenyellow;
        padding:20px;
        border: 2px solid grey;
        text-align:center;
        width:367px;
        margin:auto;
    }

    /*form{
        display:flex;
        text-align:center;
    }*/
</style>