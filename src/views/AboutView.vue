<template>
	<div class="lunch-page-container">
		<h1 class="lunch-page-header">Lunch</h1>
		<p class="luch-page-description">Scumtious recipes for lunch</p>
		<div class="recipe-cards-container flex">
			<router-link v-for="i in [0, 1, 2, 3, 4, 5, 6, 7]" :key="i" to="/recipe" class='single-recipe-card-container'>
				<img class='recipe-card-image' :src='saladPic' />
				<p class='recipe-card-title'>Salad {{i}}</p>
			</router-link>
		</div>
	</div>
</template>
<script>
import saladPic from '@/assets/img/salad.jpg'
export default {
	data() {
		return {
			saladPic: saladPic
		}
	}	
}
</script>
<style>
.lunch-page-container {}

.lunch-page-header {
	margin-top: 5rem;
}
.lunch-page-header, .luch-page-description {
	margin-left: 3rem;
}

.recipe-cards-container {
	margin-top: 3rem;
	margin-left: 3rem;
	gap: 3rem;
	width: 69rem; /*20rem * 3 + 3rem * 3*/
	flex-wrap: wrap;
}

.single-recipe-card-container {
	background-color: #fff1f1;
	height: 18.5rem; /*15rem + 3.5rem*/
	border-radius: 20px;
	text-decoration: none;
	color: black;
}
.recipe-card-image {
	border-radius: 20px 20px 0 0;
	width: 15rem;
}
.recipe-card-title {
	text-align: center;
}
</style>
