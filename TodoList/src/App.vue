<template>
    <div id="app">
        <!--med  v.bind sender man det todos array fra Data() til todosList component som får det i props se videre i todosList-->
        <TodosList v-bind:todos="todos" />
    </div>
</template>

<script>
    import TodosList from './components/TodosList.vue';

    export default {
        name: 'app',
        components: {
            TodosList
        }, 
        data() {
            return {
                todos: [
                    {
                        id: 1,
                        name: 'Make a blog Post',
                        done: true
                    },
                    {
                        id: 2,
                        name: 'Remove the clothes that are dry',
                        done: false
                    },
                    {
                        id: 3,
                        name: 'Be happy',
                        done: false
                    }
                ]
            }
        }
    };
</script>

<style>
</style>

