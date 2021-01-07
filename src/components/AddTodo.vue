<template>
    <div id="add_todo">
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add Todo ...">
            <input type="submit" value="Submit" id="submit_btn" class="btn">
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

    #add_todo {
        margin: 20px;
    }

    input[type="text"] {
        padding: 10px;
        border: 1px solid rgb(192, 94, 59);
        border-radius: 5px;
    }

    #submit_btn {
        padding: 10px;
        background: coral;
        border: 0;
        border-radius: 10px;
        margin: 10px;  
    }
    
</style>