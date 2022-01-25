<template>
    <li>
        <span v-bind:class="{done: task.completed}">
            <input type="checkbox" v-on:change="task.completed = !task.completed">
            <strong>{{index + 1}}</strong>
            {{task.title}}
        </span>
        <button class="btn-del" v-on:click="$emit('remove-task', task.id)">&times;</button>
    </li>
</template>

<script>

export default {
    props: {
        task: {
            type: Object,
            reuired: true
        },
        index: Number
    }
}
</script>

<style scoped>
    li {
        border: 1px solid black;
        border-radius: 10px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px;
        margin-bottom: 10px;
    }

    .btn-del {
        border: none;
        color: white;
        background-color: rgb(255, 133, 133);
        cursor: pointer;
        border-radius: 50%;
    }

    input {
        margin-right: 1rem;
    }

    .done {
        text-decoration: line-through;
    }
</style>