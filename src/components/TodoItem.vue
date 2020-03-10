<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markCompleted">
            {{todo.title}}
            <button class="del">X</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markCompleted(){
            this.todo.completed = !this.todo.completed;
        }
    }

}
</script>

<style scoped>

.todo-item{
    background-color: #efefef;
    color: #262626;
    padding:10px;
}
.is-completed{
    text-decoration: line-through;
}
.del{
    background: red;
    padding:10px;
    border-radius:50%;
    flex:12;
}


</style>