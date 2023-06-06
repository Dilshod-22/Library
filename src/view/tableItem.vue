<template>
    <div class="grid item grid-cols-7 bg-gray-300 items-center hover:cursor-pointer h-10">
        <h2 class="font-medium col-span-2 1text-lg pl-3">{{ libraryInfo.title }}</h2>
        <h2 class="font-medium col-span-2 text-lg pl-3">{{ libraryInfo.author }}</h2>
        <h2 class="font-medium col-span-2 text-lg pl-3">{{ libraryInfo.isbn }}</h2>
        <button class="border-black rounded-md bg-red-500 text-white w-7 h-5 text-sm hover:bg-red-700" @click="$emit('onRemove',libraryInfo.id)">X</button>
    </div>
</template>

<script>
    export default {
        props:{
            libraryInfo:{
                type:Object,
                required:true
            }
        }
    }
</script>

<style>
    .item:nth-child(even){
        background-color: white;
    }
</style>