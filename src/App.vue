<template>
	<section id="app" class="todoapp">
		<header class="header">
			<h1>todos</h1>
		</header>
		<section class="main">
			<ul class="todo-list">
				<li class="todo">
					<div class="view">
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