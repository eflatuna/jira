<template>
	<form>
		<label>Title</label>
		<input type="text" v-model="title" required />
		<label>Task Details</label>
		<textarea v-model="details" required></textarea>
		<button>Add</button>
	</form>
</template>

<script>
export default {
	data() {
		return {
			title: "",
			details: "",
		};
	},
};
</script>

<style></style>
