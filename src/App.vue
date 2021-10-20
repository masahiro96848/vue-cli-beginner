<template>
	<section id="app" class="todoapp">
		<header class="header">
			<h1>todos</h1>
            <todo-input
                :todo="todo"
                @input="onInput"

            />
		</header>
		<section class="main">
			<ul class="todo-list">
				<li class="todo">
					<div class="view">
                        <input 
                            type="checkbox"
                            class="toggle"
                        >
						<label>{{todo.title}}</label>
					</div>
				</li>
			</ul>
		</section>
	</section>
</template>

<script>
import TodoInput from './components/TodoInput.vue'
export default {
	name: 'app',
	components: {
        TodoInput,
	},
	data() {
		
    return {
			todo: {
				id: 0,
				title: 'test todo',
				completed: false
			}
		}
	},
    methods: {
        onInput(value) {
            this.todo.title = value;
        }
    },
}
</script>

<style>
@import url("https://unpkg.com/todomvc-app-css@2.2.0/index.css");
</style>