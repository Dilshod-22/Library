<template>
    <div class="h-40 w-full item">
        <div class="grid grid-cols-7 bg-gray-300 border border-black">
            <h2 class="font-medium col-span-2 text-lg pl-3">Title</h2>
            <h2 class="font-medium col-span-2 text-lg pl-3">Author</h2>
            <h2 class="font-medium col-span-2 text-lg pl-3">ISBN#</h2>
        </div>
        <tableItem v-if="libraryInfos.length"  v-for="libraryInfo in libraryInfos" :libraryInfo = "libraryInfo" @onRemove="$emit('onRemove',libraryInfo.id)"/>
        <h1 v-else class="text-center mt-3 font-medium text-xl">Informations is not found!!!</h1>
    </div>
</template>

<script>1
    import tableItem from "./tableItem.vue"
    export default{
        props:{ 
            libraryInfos:{
                type:Array,
                required:true
            }
        },
        components:{
            tableItem
        }
    }
</script>

<style>
</style>