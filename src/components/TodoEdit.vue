<template>
    <input 
        id="edit"
        class="edit"
        type="text"
        :value="todo.title"

    >
</template>

<script>
export default {
    name: 'TodoEdit',
    props: {
        todo: Object,
    }
}
</script>