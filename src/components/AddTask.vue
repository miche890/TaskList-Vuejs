<template>
	<div>
		<h2>Agregar tarea:</h2>
		<form @submit.prevent="addTask">
			<label>
				Nombre de la tarea:
				<input type="text" v-model="newTaskName" />
			</label>
			<button>Agregar</button>
		</form>
	</div>
</template>

<script>
export default {
	data() {
		return {
			newTaskName: '',
		};
	},
	methods: {
		addTask() {
			const newTask = { id: Date.now(), name: this.newTaskName };
			this.$emit('add-task', newTask);
			this.newTaskName = '';
		},
	},
};
</script>
