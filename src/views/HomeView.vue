<script setup>

</script>

<template>
    <main class="bg-blue-500 h-200 py-20">
        <div class="max-w-[470px] mx-auto bg-white p-6 rounded-lg">
            <div class="w-full flex items-center justify-between gap-4 mb-8">
                <input v-model="todo" class="w-full border-2 border-blue-500 rounded-md p-2 outline-none" type="text" placeholder="type here...">
                <button @click="add" class="bg-blue-500 text-white rounded-md px-4 py-2.5 hover:cursor-pointer">Add</button>
            </div>
        </div>
    </main>
</template>
