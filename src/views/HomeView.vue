<template>
	<div class="lunch-page-container">
		<h1 class="lunch-page-header">Lunch</h1>
		<p class="luch-page-description">Scumtious recipes for lunch</p>
		<div class="recipe-cards-container flex">
			<router-link v-for="i, x in fetchedData" @click="moveData(i)" :key="x" to="/recipe" class='single-recipe-card-container'>
				<img class='recipe-card-image' :src='i.data.meals[0].strMealThumb' />
				<p class='recipe-card-title'>Salad {{i.data.meals[0].strMeal}}</p>
			</router-link>
		</div>
	</div>
</template>
<script>
import saladPic from '@/assets/img/salad.jpg'
import axios from 'axios'

export default {
	data() {
		return {
			saladPic: saladPic,
			loading: false,
			error: null,
			fetchedData: [], 
		}
	},
	created() {
		// watch the params of the route to fetch the data again
			this.$watch(
			() => this.$route.params,
			() => {this.fetchData()},
			// fetch the data when the view is created and the data is
			// already being observed
			{ immediate: true }
		)
	},
	methods: {
		fetchData() {
			for (let i=0; i<8; i++) {
				this.error = null
				this.loading = true
				axios.get('https://www.themealdb.com/api/json/v1/1/random.php')
					.then((res) => {this.fetchedData = [...this.fetchedData, res]})
					.catch((err) => {this.error = err; console.log(err)})
						.then(() => this.loading = false)		
			}
		},
	},
	props: ['moveData']
}
</script>
<style>
.lunch-page-container {}

.lunch-page-header {margin-top: 5rem;}
.lunch-page-header, .luch-page-description {margin-left: 3rem;}
.luch-page-description {color: #afafaf}
.recipe-cards-container {
	margin-top: 3rem;
	margin-left: 3rem;
	gap: 3rem;
	width: calc(100vw - 51rem); /*20rem * 3 + 3rem * 3*/
	flex-wrap: wrap;
}
.single-recipe-card-container {
	background-color: #fff1f1;
	height: 18.5rem; /*15rem + 3.5rem*/
	border-radius: 20px;
	text-decoration: none;
	color: black;
	max-width: 15rem;
}
.recipe-card-image {border-radius: 20px 20px 0 0; width: 15rem;}
.recipe-card-title {text-align: center;}
</style>
