<template>
    <div id="app">
        <Home msg="Hello World!" />
        <!--med  v.bind sender man det todos array fra Data() til todositem component som får det i props-->
        <TodoItem v-bind:TodoItem="todos"></TodoItem>
    </div>
</template>

<script>
    import Home from './components/Home.vue';
    import TodoItem from './components/TodoItem.vue';

    export default {
        name: 'app',
        components: {
            Home,
            TodoItem
        }, 
        data() {
            return {
                todos: [
                    {
                        id: 1,
                        name: 'todoitem1',
                        done: true
                    },
                    {
                        id: 2,
                        name: 'todoitem2',
                        done: false
                    },
                    {
                        id: 3,
                        name: 'todoitem3',
                        done: false
                    }
                ]
            }
        }
    };
</script>

<style>
</style>

