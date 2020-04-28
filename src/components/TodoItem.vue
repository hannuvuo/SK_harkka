<template>
    <div class="single todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete" v-bind:checked="todo.completed">
            {{todo.title}}
            <button @click="$emit('del-todo', todo.id)" class="btn del">Poista muistutus</button>
            </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: lightblue;
        padding: 10px;
        border-bottom: 1px #ccc dotted;        
    }

    .single:hover {
        background-color: dimgrey;
    }

    .btn:hover {
        background: rgb(185, 135, 250);    
    }

    .is-complete {
        text-decoration: line-through;
        background: gold;

    }

    .del {
        background: orangered;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;        
    }
</style>