<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{ todo.title}} 
            <button @click="$emit('del-todo', todo.id)" class="del"> X </button>
        </p>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props: ['todo'],
    methods: {
        markComplete(){
            this.todo.completed =!this.todo.completed;
        }
    },
}
</script>

<style scoped lang="scss">
    .todo-item {
        padding: 10px;
    }
    .is-complete {
        text-decoration: line-through;
    }
    .del {
        background-color: red;
    }
</style>