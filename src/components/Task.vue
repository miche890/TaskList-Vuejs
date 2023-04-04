<template>
	<li :key="task.id">{{ task.name }}</li>
</template>

<script>
export default {
	props: {
		task: {
			type: Object,
			required: true,
		},
	},
};
</script>
