<template>
	<form @submit.prevent="handleSubmit()">
		<label>Title</label>
		<input type="text" v-model="title" required />
		<label>Task Details</label>
		<textarea v-model="details" required></textarea>
		<button>Add</button>
	</form>
</template>

<script>
export default {
	props: ["id"],
	data() {
		return {
			title: "",
			details: "",
		};
	},
	mounted() {
		fetch("http://localhost:3000/tasks/" + this.id)
			.then((res) => res.json())
			.then((data) => console.log(data))
			.catch((err) => console.log(err.message));
	},
};
</script>

<style></style>
