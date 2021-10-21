<template>
	<section id="app" class="todoapp">
		<header class="header">
			<h1>todos</h1>
            <TodoInput
                @add-todo="addTodo"
            />
		</header>
		
        <TodoList 
            :todos="todos"
            :filtered-todos="filteredTodos"
        />
	</section>
</template>

<script>
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
export default {
	name: 'app',
	components: {
        TodoInput, TodoList,
	},
	data() {
		
    return {
			todos: [
				{
					id: 0,
					title: '項目0',
					completed: false
				},
				{
					id: 1,
					title: '項目1',
					completed: false
				}
			]
		}
	},
    computed: {
        filteredTodos(){
            return this.todos
        }
    },
    methods: {
        addTodo(todoTitle) {
            const newTodo = todoTitle && todoTitle.trim();
            if(!newTodo){
                return
            }
            this.todos[0].title = newTodo;
        }
    },
}
</script>

<style>
@import url("https://unpkg.com/todomvc-app-css@2.2.0/index.css");
</style>