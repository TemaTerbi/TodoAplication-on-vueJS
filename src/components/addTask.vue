<template>
    <form @submit.prevent="onSubmit">
        <input type="text" v-model="title">
        <button type="submit">Add</button>
    </form>
</template>


<script>
export default {
    data() {
        return{
            title: ''
        }
    },
    methods: {
        onSubmit(){
            if(this.title.trim()){
                const newTask = {
                    id: Date.now(),
                    title: this.title,
                    completed: false
                }
            this.$emit('add-task', newTask)
            this.title = ''
            }
        }
    }
}
</script>



<style scoped>
    form {
        display: flex;
        margin-bottom: 30px;
    }

    input {
        margin-right: 1rem;
    }
</style>