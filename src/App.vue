<template>
	<div>
		<h1>Lista de tareas pendientes</h1>
		<TaskList :tasks="tasks" />
		<AddTask @add-task="addTask" />
	</div>
</template>

<script>
import TaskList from './components/TaskList.vue';
import AddTask from './components/AddTask.vue';

export default {
	components: {
		TaskList,
		AddTask,
	},
	data() {
		return {
			tasks: [
				{ id: 1, name: 'Comprar leche' },
				{ id: 2, name: 'Pagar la factura de la luz' },
				{ id: 3, name: 'Llamar al dentista' },
			],
		};
	},
	methods: {
		addTask(newTask) {
			this.tasks.push(newTask);
		},
	},
};
</script>

<style scoped>
header {
	line-height: 1.5;
}

.logo {
	display: block;
	margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
	header {
		display: flex;
		place-items: center;
		padding-right: calc(var(--section-gap) / 2);
	}

	.logo {
		margin: 0 2rem 0 0;
	}

	header .wrapper {
		display: flex;
		place-items: flex-start;
		flex-wrap: wrap;
	}
}
</style>
