<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" class="checkbox" v-on:change="markComplete(todo)">
            {{ todo.title }}
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>    
</template>

<script>
export default {
    name: "Todoitem",
    props: ["todo"],
    methods: {
        markComplete(todo) {
            todo.completed = !todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background-color: #f4f4f4;
        
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .checkbox {
        margin-right: 10px;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background-color: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>
