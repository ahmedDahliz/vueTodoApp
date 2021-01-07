<template>
    <div>
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
</style>