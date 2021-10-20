<template>
	<section id="app" class="todoapp">
		<header class="header">
			<h1>todos</h1>
            <input 
                class="new-todo"
                autofocus autocomplete="off"
                type="text" 
                placeholder="What needs to be done"
                v-model="todo.title"

            >
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
export default {
	name: 'app',
	components: {
	},
	data() {
		return {
			todo: {
				id: 0,
				title: 'test todo',
				completed: false
			}
		}
	}
}
</script>

<style>
@import url("https://unpkg.com/todomvc-app-css@2.2.0/index.css");
</style>