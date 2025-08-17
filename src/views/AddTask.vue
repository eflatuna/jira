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
	data() {
		return {
			title: "",
			details: "",
			uri: "http://localhost:3000/tasks/",
		};
	},
	methods: {
		handleSubmit() {
			let task = {
				id: Math.floor(Math.random() * 100000),
				title: this.title,
				details: this.details,
				complete: false,
			};

			fetch(this.uri, {
				method: "POST",
				headers: { "Content-Type": "application/json" },
				body: JSON.stringify(task),
			})
				.then(() => {
					this.$router.push("/");
				})
				.catch((err) => console.log(err.message));
		},
	},
};
</script>

<style>
form {
	box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
	padding: 20px;
	margin: 20px 0px;
	background-color: white;
	border-radius: 20px;
}
label {
	display: block;
	margin: 20px 0px 10px;
	letter-spacing: 1px;
	font-size: 15px;
	font-weight: 500;
}
input {
	padding: 10px;
	font-size: 15px;
	border: 1px solid #ddd;
	border-radius: 4px;
	width: 100%;
	height: 40px;
	margin-bottom: 20px;
	outline: none;
}
textarea {
	padding: 10px;
	font-size: 15px;
	border: 1px solid #ddd;
	border-radius: 4px;
	width: 100%;
	height: 100px;
	margin-bottom: 20px;
	outline: none;
}
button {
	background-color: #4caf50;
	color: white;
	padding: 14px 20px;
	margin: 8px 0;
	border: none;
	cursor: pointer;
	width: 100%;
	border-radius: 4px;
	font-size: 16px;
}
</style>
