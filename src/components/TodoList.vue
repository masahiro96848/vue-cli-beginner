<template>
    <section class="main" v-show="todos.length" v-cloak>
        <input 
            id="toggle-all" class="toggle-all" type="checkbox"
            :value="allDone"
            :checked="allDone"
            @change="onInput"
        >
        <label for="toggle-all"></label>
        <ul class="todo-list">
            <li v-for="todo in filteredTodos"
                class="todo"
                :class="{completed: todo.completed, editing: todo === editedTodo}"
                :key="todo.id"
            >
            <TodoItem
                :todo="todo"
                @remove-todo="removeTodo"
                @done="done"
                @edit-todo="editTodo"
            />
            <TodoEdit 
                :todo="todo"
                @done-edit="doneEdit"
                @cancel-edit="cancelEdit"
            />

            </li>
        </ul>
    </section>
</template>

<script>
import TodoItem from './TodoItem.vue'
import TodoEdit from './TodoEdit.vue'

export default {
    name: 'TodoList',
    components: {
        TodoItem, TodoEdit
    },
    data() {
        return {
            editedTodo: null
        };
    },
    props: {
        todos: Array,
        filteredTodos: Array,
        allDone: Boolean,
    },
    methods: {
        removeTodo(todo) {
            this.$emit('remove-todo', todo);
        },
        done(todo, completed) {
            this.$emit('done', todo, completed)
        },
        onInput(){
            this.$emit('allDone', !this.allDone)
        },
        editTodo(todo){
            this.editedTodo = todo;
        },
        doneEdit(todoTitle){
            if(!this.editedTodo) {
                return;
            }
            const title = todoTitle.trim();
            if(title) {
                this.editedTodo.title = title;
            } else {
                this.removeTodo(this.editedTodo);
            }
            this.editedTodo = null;
        },
        cancelEdit() {
            this.editedTodo = null;
        }
    },

}
</script>

<style scoped>
[v-cloak] {
	display: none;
}
</style>