<template>
	<div>
		<h2>Tareas pendientes:</h2>
		<ul>
			<Task v-for="(task, index) in tasks" :key="index" :task="task" />
		</ul>
	</div>
</template>

<script>
import Task from './Task.vue';

export default {
	components: {
		Task,
	},
	props: {
		tasks: {
			type: Array,
			default: () => [],
		},
	},
	watch: {
		tasks: {
			handler() {
				// nada que hacer aquí, solo mira los cambios
			},
			deep: true,
		},
	},
};
</script>
