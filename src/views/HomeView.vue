<script setup>
import ToDoItem from "@/components/ToDoItem.vue";
import {reactive, ref} from "vue";
const todo = ref('')
const todoList = reactive([])

const add = () => {
    if (todo.value !== '') {
        todoList.unshift(todo.value)
        todo.value = ''
    }
}

const remove = (index) => {
    todoList.splice(index, 1)
}
</script>

<template>
    <main class="bg-blue-700 min-h-dvh py-20 ">
        <div class="max-w-[470px] mx-auto bg-white p-6 rounded-lg">
            <h1 class="text-3xl font-semibold leading-[1.5] text-center pb-4">ToDo List</h1>
            <div class="w-full flex items-center justify-between gap-4 mb-4">
                <input v-model="todo" class="w-full border-2 border-blue-500 rounded-md p-2 outline-none focus:ring-2 focus:ring-blue-500" type="text" placeholder="Enter your task...">
                <button @click="add" class="bg-blue-700 text-white rounded-md px-4 py-2.5 hover:cursor-pointer active:bg-blue-900">Add</button>
            </div>
            <ToDoItem v-for="(item, index) in todoList" :key="index" :text="item" @delete-item="remove(index)" />
        </div>
    </main>
</template>
