<template>
    <div class="TodosList">
        <!--almindelig forloop samme navn som det array vi får passed-->
        <!--når vi looper, har vi brug for en key for hver item, bind laver det for os og binder det id til hvert todositem-->
        <div v-bind:key="todoitem.id" v-for="todoitem in todos">
            <!-- TodoItem kan blive embeded -->
            <!-- for hver interation vil vi gerne binde de todoitem til det embedede Todoitem -->
            <!-- sender hvert enkelt item nu til TodoItem til deres props -->
            <TodoItem v-bind:todoitem="todoitem"/>
        </div>
    </div>
</template>

<script>
    // for at TodosItem kan blive brugt skal det importeres
    // da det ligger i samme mappe (components) er det her nok.
    import TodoItem from './TodoItem.vue';

    export default {
        //navn af det component
        name: "TodosList",

        //de components der bliver importeres skal tilføjes her for at kunne blive brugt
        components: {
            TodoItem
        },
        //her kommer de props fra App component hen til.
        //bliver gemt i et array der modtager "todos" samme navn som det der blev sendt.
        //i vue dev tools kan an nu se at de data blev passed til det her component
        props: ["todos"]
    }
</script>

<style scoped>
</style>