<template>
    <header class="header">
        <h1>Todo List</h1>
    </header>
</template>
<script>
export default {
    name: "Header"

}
</script>

<style scoped>
.header{
    display: flex;
    background: #BDBDBD;
    justify-content: center;
    color: #262626;
    padding:1.5rem;
}
.header a{
    padding:2rem;
    font-family:Arial, Helvetica, sans-serif;
}
</style>