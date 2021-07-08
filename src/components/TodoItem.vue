<template>
    <div class="todo" :class="{isFinished: todo.isFinished}">
        <div class="todo-body">
            <input type="checkbox" 
            :checked="todo.isFinished ? 'checked': '' "
            v-on:change="checkTodo"
            >
            {{todo.title}}
        </div>

        <div class="todo-actions">
            <button @click="$emit('deleteTodo', todo.id)">Delete</button>
        </div>
    </div>
</template>
    
<script>
export default {
    name: 'ToddoItem',
    props: ['todo'],

    methods: {
        checkTodo(){
            this.todo.isFinished = !this.todo.isFinished
        },

        update(){
            
        }
    }
}
</script>
    
<style scoped>
    .todo{
        border-bottom: solid 1px #ccc;
        padding: 10px;
    }

    .todo:not(.isFinished):hover{
        background-color: #eee;
    }

    .isFinished{
        color: #ccc;
        text-decoration: line-through;
    }

    .isFinished .todo-body{
        text-decoration: line-through;
    }

    .todo-body, .todo-actions{
        display: inline-block;
        vertical-align: top;
    }

    .todo-body{
        width: 85%;
    }

    .todo-actions{
        padding: 0 10px;
        width: 10%;
    }

    button{
        border: none;
        border-radius: 3px;
        margin-left: -80%;
        padding: 10px;
        background-color: #ccc;
        color: black;
    }

    button:hover{
        background-color: #da2020;
        color: white;
    }

</style>  