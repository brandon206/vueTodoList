<template>
    <div>
        <!-- v-for goes in a loop -->
        <!-- todoItem refers to each object inside the todos list that was passed in -->
        <!-- todos referes to the array of todos that was passed in from props -->
        <!-- <div v-bind:key="todoItem.id" v-for="todoItem in todos">
            <h3>{{todoItem.title}}</h3>
        </div> -->

        <div v-bind:key="todo.id" v-for="todo in todos">
            <TodoItem v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
    name: "Todos",
    components: {
        TodoItem
    },
    props: ["todos"]
}
</script>


<style scoped>

</style>
