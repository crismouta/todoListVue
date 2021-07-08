<template>
    <div id="add-container">
        <form @submit="addTodo">
            <input type="text" v-model="title" placeholder="Type your task">
        </form>
    </div>
</template>

<script>

import { uuid } from 'vue-uuid'
export default {
    name: 'TodoList',

    data () {
        return {
            title: ''
        }
    },

    methods: {
        addTodo(e){
            e.preventDefault()

            const newTodo = {
                id: uuid.v4(),
                title: this.title,
                isFinished: false
            }

            this.title =''
            this.$emit('addTodo', newTodo)

        }
    }
}
</script>

<style scoped>

    #add-conteiner{
        padding: 10px
    }

    input{
        padding: 10px;
        outline: none;
        border: 1px solid #ccc;
        width: 100%;
        font: bold 1.5rem 'Open Sans', sans-serif;

    }

</style>