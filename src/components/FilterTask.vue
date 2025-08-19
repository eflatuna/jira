<template>
	<nav>
		<button @click="updateFilter('all')">All</button>
		<button @click="updateFilter('completed')">Completed</button>
		<button @click="updateFilter('contunied')">Countunied</button>
	</nav>
</template>

<script>
export default {
	emits: {
		filterChange: null,
	},
	props: ["current"],
	methods: {
		updateFilter(filterValue) {
			this.$emit("filterChange", filterValue);
		},
	},
};
</script>

<style></style>
