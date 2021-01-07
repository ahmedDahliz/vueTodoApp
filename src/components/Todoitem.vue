<template>
    <div id="todo_item">
        <p v-bind:class="{'is-complete': todo.completed}">
            <input type="checkbox" v-on:change="markComplete(todo.completed)" >
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)">x</button>
            </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    data (){
            return{
                todoitem : this.todo
            }
    },
    methods:{
        markComplete (isComplited){
            console.log(isComplited);
            this.todoitem.completed = !isComplited
        }
    }
}
</script>

<style scoped>
    .is-complete {
        text-decoration: line-through;
    }
    #todo_item {
        background: wheat;
        padding: 10px;
        margin: 0;
    }
    #todo_item button {
        border-radius: 10px;
        border: 1px solid rgb(66, 4, 4);
        background: red;
        color: white;
        float: right;
    }
</style>