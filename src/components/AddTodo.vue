<template>
    <form @submit.prevent="onSubmit">
        <input type="text" v-model="title">

        <button> Create </button>
    </form>
</template>

<script>
export default {
    name: 'AddTodo',

    data () {
        return {
            title: ''
        }
    },

    methods: {
        onSubmit () {
            if (this.title.trim()) {
                const newTodo = {
                    id: Date.now(),
                    title: this.title,
                    completed: false
                }

                this.$emit('add-todo', newTodo)
            } 
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
        justify-content: center;
    }

    input {
        width: 400px;
    }
</style>