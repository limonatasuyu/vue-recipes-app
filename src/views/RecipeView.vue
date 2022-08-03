<template>
	<div className="recipe-page-container">
		<h1>Salad</h1>
		<p>Lorem ipsum dolor sit amet</p>
		<div class="recipe-page-food-card flex">
			<img class="food-card-image" :src="saladPic"/>
			<div class="food-card-text grid">
				<p>Prep: 5min</p>
				<p>Cook: 5min</p>
				<p>Total: 1hr35min</p>
				<p>Servings: 8</p>
				<p>Yields: 8 servings</p>
			</div>
		</div>
		<div class="ingredients-wrapper">
			<h1>Ingredients</h1>
			<ol><li>Lorem</li><li>Ipsum</li><li>Dolor</li><li>Sit</li><li>Amet</li></ol>
		</div>
		<hr />
		<div class="directions-wrapper">
			<h1>Directions</h1>
			<ol><li>Lorem</li><li>Ipsum</li><li>Dolor</li><li>Sit</li><li>Amet</li></ol>
		</div>
		<hr />
		<div class="tips-wrapper">
			<p>Tips:</p>
			<p>Consider xyz lorem ipsum dolor sit amet</p>
		</div>
	</div>
</template>
<style>
.recipe-page-container {
	margin-left: 3rem;
}
.recipe-page-food-card {
	background-color: #fff1f1;
	width: calc(100vw - 20rem - 6rem);
	border-radius: 10px
}
.food-card-image {
	width: 20rem;
	border-radius: 	10px 0 0 10px;
}

.food-card-text {
	margin-left: 2.5rem;
	align-content: center;
	gap: 1.4rem;
	font-size: 1.4rem;
}
.food-card-text p {margin: 0; padding: 0;}

.ingredients-wrapper, .directions-wrapper, .tips-wrapper {margin-top: 3rem;}

.ingredients-wrapper ol li, .directions-wrapper ol li {margin-top: .5rem;}

hr {background-color: #7ecefece; border: none; height: 1px;}

</style>
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
