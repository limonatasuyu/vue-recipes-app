<template>
	<div v-if='data' className="recipe-page-container">
		<h1>{{data.meals[0].strMeal}}</h1>
		<div class="recipe-page-food-card flex">
			<img class="food-card-image" :src="data.meals[0].strMealThumb"/>
			<div class="ingredients-wrapper">
				<h1>Ingredients</h1>
				<div class="ingredients-items flex">
					<li v-for="(i, x) in getIngredientsList" :key='x'>{{i}}</li>
				</div>
			</div>
		</div>
		<div class="instructions-wrapper">
			<h1>Instructions</h1>
			<p>{{data.meals[0].strInstructions}}</p>
		</div>
		<hr />
	</div>
</template>


<style>
.recipe-page-container {
	margin-left: 2vw;
}
.recipe-page-food-card {
	background-color: #fff1f1;
	width: calc(100vw - 40rem);
	border-radius: 10px
}
.food-card-image {
	width: 20rem;
	border-radius: 	10px 0 0 10px;
}
.ingredients-wrapper {margin-left: 2rem;}
.instructions-wrapper, .ingredients-wrapper {margin-top: 3rem;}
.instructions-wrapper p {margin-top: .5rem; max-width: 80rem}
hr {background-color: #7ecefece; border: none; height: 1px;}
.ingredients-items {
	flex-direction: column;
	flex-wrap: wrap;
	max-height: 10rem;
	gap: .2rem;
}
.recipe-page-container {color: #AFAFAF}

@media screen and (max-width: 1470px) {
	.recipe-page-food-card {
		background-color: inherit;
		display: block
	}
	.food-card-image {border-radius: 0;}
}

@media screen and (max-width: 1030px) {
	.ingredients-items {
		flex-wrap: nowrap;
		max-height: 100%;
	}
	
	.recipe-page-food-card {width: 100%}
}
</style>

<script>

export default {
	data() {
		return {
			data: this.movingData.data,
		}
	},
	computed: {
		getIngredientsList() {
			var obj = this.data['meals'][0]
			var keys = Object.keys(obj)
			var ingredientPattern = /strIngredient/
			var ingredientKeys = keys.filter((str) => {return ingredientPattern.test(str)})
			var ingredientList = ingredientKeys.map((i) => {return obj[i]})
			
			var measurePattern = /strMeasure/
			var measureKeys = keys.filter((str) => {return measurePattern.test(str)})
			var measureList = measureKeys.map((i) => {return obj[i]})
			
			var returnList = ingredientList.map((i, x) => {return measureList[x] + " " + i })
			returnList = returnList.filter((i) => {return i !== ' '})
			return returnList
		}
	},
	props: ['movingData']
}
</script>
