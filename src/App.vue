<template>
	<div class="app-container flex">
		<div class='main-nav'>
			<router-link class='nav-logo' to="/">Logo placeholder</router-link>
			<router-link class='nav-page' to="/">Recipes</router-link>
			<div class='white-circle' />
			<div class='white-circle' />
			<div class='white-circle' />
		</div>
		<router-view :moveData="moveData" :movingData="movingData"/>
	</div>
</template>
<script>
export default {
	data() {return {
			movingData: null	
		}
	},
	methods: {
		moveData(data) {this.movingData = data}
	}
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Rakkas&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');
/*font-family: 'Rakkas', cursive;*/
/*font-family: 'Roboto', sans-serif;*/

html, body {
	padding: 0;
	margin: 0;
	font-family: 'Roboto', sans-serif;
}
h1 {color: #fb693c}


.flex {display: flex}
.grid {display: grid}

.app-container {}
.main-nav {
	display: grid;
	background-color: #ffe1e1;
	grid-gap: 1rem;
	width: 15rem;
	height: 100vh;
	align-content: flex-start;
	position: sticky;
	top: 0;
	font-size: 1.5rem;
}
.nav-logo {margin-top: 5rem; font-family: 'Rakkas', cursive; color: #fb693c;}
.nav-logo, .nav-page {text-decoration: none; margin-left: 1.1vw}
.nav-page {color: #a07568; margin-top: 3rem}
.nav-page:hover {color: #c09588}

.white-circle {
	width: 2rem;
	height: 2rem;
	border-radius: 50px;
	background-color: white;
	margin-left: 2rem;	
}
.white-circle:first-of-type {margin-top: 5rem;}

@media screen and (max-width: 1370px) {
	.main-nav {padding-right: 1rem;}
}
@media screen and (max-width: 625px) {
	.main-nav {width: 9rem}
}
</style>
