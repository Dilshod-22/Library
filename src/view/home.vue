<template>
  <div class="w-[700px] h-[550px]">
    <h1 class="text-4xl font-normal mt-5 text-center">
      My
      <span class="text-blue-600"> Book </span>
      List
    </h1>
    <addFrom @addItemHandler="addItemHandler"/>
    <tableList :libraryInfos = "libraryInfos" @onRemove="onRemoveHandler"/>
</div>
</template>

<script>
import addFrom from './addFrom.vue';
import tableList from "./tableList.vue"
export default {
    data(){
        return{
            libraryInfos:[
                {
                    title:"otgan kunlar",
                    author:"otkir hoshimov",
                    isbn:123,
                    id:1
                },
                {
                    title:"oq kema",
                    author:"oybek",
                    isbn:124,
                    id:2
                },{
                    title:"may",
                    author:"umar hayyom",
                    isbn:125,
                    id:3
                }
            ],
        }
    },
    components:{
        addFrom,
        tableList,
    },
    methods:{
        onRemoveHandler(id){  
            this.libraryInfos = this.libraryInfos.filter(c => c.id !== id)
        },
        addItemHandler(item){
            this.libraryInfos.push(item)
        }   
    }
};
</script>

<style></style>
