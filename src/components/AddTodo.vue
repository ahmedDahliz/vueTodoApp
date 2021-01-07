<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Todo ...">
            <input type="submit" value="Submit">
        </form>
    </div>
</template>

<script>

// import {v4 as uuid} from "uuid";

export default {
    name: 'AddTodo',
    data() {
        return {
            title: '',
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();
            this.$emit('add-todo', this.title);
            this.title = ''; 
        }

    }
}
</script>

<style scoped>

    
</style>