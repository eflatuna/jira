<template>
	<div class="task">
		<div class="actions">
			<h3 @click="toggleDetail">{{ task.title }}</h3>
		</div>
		<div class="details" v-if="showDetails">
			<p>{{ task.details }}</p>
		</div>
	</div>
</template>

<script>
export default {
	props: ["task"],
	data() {
		return {
			showDetails: false,
		};
	},
	methods: {
		toggleDetail() {
			this.showDetails = !this.showDetails;
		},
	},
};
</script>

<style>
.task {
	box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
	padding: 10px 20px;
	margin: 20px 0px;
	background-color: white;
	border-radius: 20px;
	border-left: 8px solid palevioletred;
}
h3 {
	cursor: pointer;
}
.details {
	padding: 20px 0px;
}

.actions {
	padding: 15px 0px;
}
</style>
