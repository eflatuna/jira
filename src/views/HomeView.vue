<template>
	<div v-if="tasks.length">
		<div v-for="task in tasks" :key="task.id">
			<SingleTask
				:task="task"
				@deleteTask="handleDelete"
				@complete="handleComplete"
			/>
		</div>
	</div>
</template>

<script>
import SingleTask from "../components/SingleTask.vue";
import FilterTask from "../components/FilterTask.vue";
export default {
	name: "HomeView",
	components: {
		SingleTask,
		FilterTask,
	},

	data() {
		return {
			tasks: [],
		};
	},
	mounted() {
		fetch("http://localhost:3000/tasks")
			.then((res) => res.json())
			.then((data) => (this.tasks = data))
			.catch((err) => console.log(err.message));
	},
	methods: {
		handleDelete(id) {
			this.tasks = this.tasks.filter((task) => {
				return task.id !== id;
			});
		},
		handleComplete(id) {
			let myTask = this.tasks.find((task) => {
				return task.id === id;
			});
			myTask.complete = !myTask.complete;
		},
	},
};
</script>
