<template>
    <div>
        <div class="todo">
            <div v-for="todo in todoList" :key="todo.id">
                
                <TodoItem :todo="todo" v-on:deleteTodo="deleteTodo"/>
                
            </div>

            <TodoAdd v-on:addTodo="addTodo"/>
        </div>

    </div>
</template>

<script>
import TodoItem from './TodoItem.vue'
import TodoAdd from './TodoAdd.vue'
import axios from "axios"

export default {
    name: 'TodoList',

    components: {
        TodoItem,
        TodoAdd
    },


    data () {
        return {
            todoList: []
        }
    },

    created() {
        fetch('http://localhost:3000/todolist').then(response => {
        return response.json();
        })
        .then(data =>{
            this.todoList = data;
        })
    },
    
    methods: {
        deleteTodo(id) {
            
            this.todoList = this.todoList.filter(todo => todo.id != id)
        },

        addTodo(todo){
            this.todoList.push(todo)
        }
    }


}
</script>

<style scoped>

    .todo{
        margin: auto;
        text-align: left;
        font: bold 1.5rem 'Open Sans', sans-serif;

    }

</style>