<template>
    <input 
        type="text"
        class="new-todo"
        autofocus autocomplete="off"
        placeholder="What needs to be done"
        :value="todo.title"
        @input="onInput"
    >
</template>

<script>
export default {
    name: 'TodoInput',
    props: {
        todo: Object,
    },
    methods: {
        onInput(event) {
            this.$emit('input', event.target.value);
        }
    },
}
</script>