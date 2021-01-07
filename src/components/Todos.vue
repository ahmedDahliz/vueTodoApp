<template>
    <div id="todos">
        <div id="todo" v-for="todo in todos" v-bind:key="todo.id">
            <Todoitem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
        </div>
    </div>
</template>

<script>
import Todoitem from './Todoitem.vue'

export default {
    name: "Todos",
    props: ["todos"],
    components:{
        Todoitem
    }
        
}
</script>

<style scoped>
    #todo {
        text-align: left;
        width: 50%;
        margin: auto;
        border-bottom: 1px solid rgb(66, 4, 4);
        border-right: 1px solid rgb(66, 4, 4);
        border-left: 1px solid rgb(66, 4, 4);        
    }

    #todo:nth-child(1) {
         border: 1px solid rgb(66, 4, 4);
    }



   
</style>