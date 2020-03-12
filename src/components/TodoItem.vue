<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
        <p>
            <input type="checkbox" class="checkbox" v-on:change="markCompleted">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" class="del">X</button>
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
    border-bottom: 1px solid #262626;
}
.is-completed{
    text-decoration: line-through;
}
.checkbox{
    cursor: pointer;
}
.del{
    background: red;
    color:#efefef;
    border: none;
    border-radius:50%;
    padding:5px 9px;
    cursor: pointer;
    float: right;

}


</style>