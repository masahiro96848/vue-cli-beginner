<template>
    <input 
        type="text"
        class="new-todo"
        v-model="newTodo"
        @keypress="addTodo"
        autofocus autocomplete="off"
        placeholder="What needs to be done"
    >
</template>

<script>
export default {
    name: 'TodoInput',
    props: {
        todo: Object,
    },
    data() {
        return {
            newTodo: '',
        }
    },
    methods: {
        addTodo(){
            this.$emit('add-todo', this.newTodo)
            this.newTodo = '';
        }
    },
}
</script>