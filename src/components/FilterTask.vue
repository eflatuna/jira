<template>
	<nav class="filter">
		<button
			@click="updateFilter('all')"
			:class="{ active: current === 'all' }"
		>
			All
		</button>
		<button
			@click="updateFilter('completed')"
			:class="{ active: current === 'completed' }"
		>
			Completed
		</button>
		<button
			@click="updateFilter('continued')"
			:class="{ active: current === 'continued' }"
		>
			Continued
		</button>
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

<style>
.filter {
	display: flex !important;
	align-items: center;
	gap: 10px;
	flex-wrap: wrap;
}

.filter > button {
	flex: 0 0 auto;
	width: auto !important; /* width:100% gibi kuralları ezer */
	display: inline-flex !important;
	align-items: center;
	justify-content: center;
	margin: 0; /* reset */
	padding: 10px;
	background-color: bisque;
	color: gray;
	font-size: 15px;
	font-weight: bold;
	border-radius: 5px;
	cursor: pointer;
}

.active {
	color: black !important;
}
</style>
