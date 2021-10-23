<template>
    <input 
        id="edit"
        class="edit"
        type="text"
        :value="todo.title"
        @input="onInput"
        @keypress.enter="doneEdit"

    >
</template>

<script>
export default {
    name: 'TodoEdit',
    props: {
        todo: Object,
    },
    data() {
        return {
            editedTitle: null
        };
    },
    mounted() {
        this.editedTitle = this.todo.title;
    },
    methods: {
        onInput(event) {
            this.editedTitle = event.target.value;
        },
        doneEdit(event) {
            this.editedTitle = event.target.value;
            this.$emit('done-edit', this.editedTitle)
        }
    },
}
</script>