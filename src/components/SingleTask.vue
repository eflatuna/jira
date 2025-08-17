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

<style></style>
