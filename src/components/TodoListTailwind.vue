<template>
    <div>
        <!-- component -->
        <div  class="h-100 w-full flex items-center justify-center bg-teal-lightest font-sans">
            <div class="bg-white rounded shadow p-6 m-4 w-full lg:w-3/4 lg:max-w-lg">
                <div class="mb-4">
                    <h1 class="text-grey-darkest">Todo List</h1>
                    <div class="flex mt-4">
                        <input class="shadow appearance-none border rounded w-full py-2 px-3 mr-4 text-grey-darker" placeholder="Add Todo">
                        <button class="flex-no-shrink p-2 border-2 rounded text-teal border-teal hover:text-white hover:bg-teal">Add</button>
                    </div>
                </div>
                <div v-for="todo in todos" :key="todo">
                    <div  class="flex mb-4 items-center">
                        <p class="w-full text-grey-darkest">{{todo.title}}</p>
                        <button class="flex-no-shrink p-2 ml-4 mr-2 border-2 rounded hover:text-white text-green border-green hover:bg-green">Done</button>
                        <button class="flex-no-shrink p-2 ml-2 border-2 rounded text-red border-red hover:text-white hover:bg-red">Remove</button>
                    </div>
                    <div class="flex mb-4 items-center">
                        <p class="w-full line-through text-green">{{todo.title}}</p>
                        <button class="flex-no-shrink p-2 ml-4 mr-2 border-2 rounded hover:text-white text-grey border-grey hover:bg-grey">Not Done</button>
                        <button class="flex-no-shrink p-2 ml-2 border-2 rounded text-red border-red hover:text-white hover:bg-red">Remove</button>
                    </div>
                </div>
            </div>
        </div>
        <!-- component -->
    </div>
    
</template>

<script>
export default {
    name: 'TodoListTailwind',

    data () {
        return {
            todos: []
        }
    },

    created() {
        fetch('http://localhost:3000/todolist').then(response => {
        return response.json();
        })
        .then(data =>{
            this.todos = data;
        })
    } 


}
</script>

<style>

</style>