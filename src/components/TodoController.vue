<template>
    <footer class="footer" v-show="todos.length" v-cloak>
        <span class="todo-count">
            <strong>{{ remaining}}</strong> {{ remaining | pluralize}} left
        </span>
        <ul class="filters">
            <li><a href="#/all" :class="{selected: visibility === 'all'}">全て</a></li>
            <li><a href="#/active" :class="{selected: visibility === 'active'}">未処理</a></li>
            <li><a href="#/completed" :class="{selected: visibility === 'completed'}">完了</a></li>
        </ul>
    </footer>
</template>

<script>
export default {
    name: 'TodoController',
    filters: {
		pluralize(n) {
			return n === 1 ? 'item' : 'items';
		}
	},
	props: {
		todos: Array,
		remaining: Number,
		visibility: String
	}
}
</script>