<template>
	<div class="app-container flex">
		<div class='main-nav'>
			<router-link class='nav-logo' to="/">Logo placeholder</router-link>
			<router-link class='nav-page' to="/about">Breakfast</router-link>
			<router-link class='nav-page' to="/about">Lunch</router-link>
			<router-link class='nav-page' to="/about">Dinner</router-link>
			<router-link class='nav-page' to="/about">Dessert</router-link>
			<router-link class='nav-page' to="/about">Appetizers</router-link>
			<div class='white-circle' />
			<div class='white-circle' />
		</div>
		<router-view/>
	</div>
</template>

<style>
html, body {
	padding: 0;
	margin: 0;
}

.flex {display: flex}
.grid {display: grid}

.app-container {}
.main-nav {
	display: grid;
	background-color: #ffe1e1;
	grid-gap: 1rem;
	width: 18rem;
	height: 100vh;
	align-content: flex-start;
	position: sticky;
	top: 0;
	font-size: 1.8rem;
}
.nav-logo {
	margin-top: 5rem;
}
.nav-logo, .nav-page {
	text-decoration: none;
	color: black;
	margin-left: 2rem;
}
.nav-page:nth-child(2) {margin-top: 3rem}

.white-circle {
	width: 2rem;
	height: 2rem;
	border-radius: 50px;
	background-color: white;
	margin-left: 2rem;	
}
.white-circle:first-of-type {
	margin-top: 5rem;
}
</style>
