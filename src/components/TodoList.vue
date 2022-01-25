<template>
    <div>
        <ul>
            <TodoItem v-for="(task, i) in todos" v-bind:task="task" v-on:remove-task="removeTask" v-bind:index="i"/>
        </ul>
    </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'
export default {
    props: ['todos'],
    components: {
        TodoItem
    },
    methods: {
        removeTask(id){
            this.$emit('remove-task', id)
        }
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>
