<template>
    <div>
        <form @submit='addTodo'>
            <input type="text" v-model="title" name="title" placeholder="Add Todo...">
            <input type="submit" value="Submit" class="submit-btn">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';

export default {
    name: 'AddTodo',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = { 
                id: uuid.v4(),
                title: this.title,
                completed: false
            }
            // Send up to parent
            this.$emit('add-todo', newTodo);
            // CLear form
            this.title = '';
        }
    },
}
</script>

<style scoped lang="scss">
    .submit-btn {
        background-color: green;
    }
</style>