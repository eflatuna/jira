<template>
	<div class="task">
		<div class="actions">
			<h3>{{ task.title }}</h3>
		</div>
		<div class="details">
			<p>{{ task.details }}</p>
		</div>
	</div>
</template>

<script>
export default {
	props: ["task"],
};
</script>

<style></style>
