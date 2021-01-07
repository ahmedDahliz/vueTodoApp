<template>
    <div id="header">
        <h1>Todos List</h1>
        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">About</router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped>
    #header {
        padding: 10px;
        background-color: antiquewhite;
    }
</style>