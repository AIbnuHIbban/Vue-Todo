<template>
    <div class="todo-item" :class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" @change="jadikanComplete">
            {{ todo.title }} 
            <button @click="$emit('del-todo', todo.id)" class="del">x</button>
        </p>
    </div>
</template>

<script>

export default {
    name: "TodoItem",
    props: ['todo'],
    methods: {
        jadikanComplete(){
            this.todo.completed = !this.todo.completed
        }
    },
}
</script>

<style scoped>
    .todo-item{
        background: whitesmoke;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }
    .is-complete{
        text-decoration: line-through;
    }
    .del{
        background: red;
        color: white;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>
