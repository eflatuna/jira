<template>
	<nav class="mainNav">
		<router-link to="/">Todo List</router-link>
		<router-link to="/addTask">Add New Todo </router-link>
	</nav>
	<router-view />
</template>

<style>
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
body {
	background-color: ghostwhite;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	max-width: 600px;
	width: 100%;
	margin: 0px auto;
}

.mainNav {
	text-align: center;
	margin: 40px 0px;
}

.mainNav a {
	text-decoration: none;
	color: gray;
	font-size: 18px;
	margin: 0px 10px;
}

a.router-link-active {
	color: palevioletred;
	padding-bottom: 4px;
}
</style>
