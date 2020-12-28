<template lang="">
	<div>
		<!-- Breaking Bad -->
		<Header></Header>
		<Search v-on:wordChange="onWordChange"></Search>
		<Actors></Actors>
	</div>
</template>
<script>
	import Header from "./components/Header";
	import Search from "./components/Search";
	import Actors from "./components/Actors";
	import axios from "axios";

	export default {
		name: "App",
		components: {
			Header,
			Search,
			Actors
		},
		mounted() {
			axios
				.get("https://www.breakingbadapi.com/api/characters", {})
				.then((response) => {
					this.datas = response.data;
					console.log(response.data);
				})
				.catch(function(error) {
					console.log(error);
				});
			//This is how to get all data from the api endpoint with axios
		},
		methods: {
			onWordChange: function(searchTerm) {
				console.log(searchTerm);
			}
		}
	};
</script>
<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	body {
		font-family: "Montserrat";
		color: white;
		background: rgb(0, 0, 0);
		background: linear-gradient(
			90deg,
			rgba(0, 0, 0, 1) 0%,
			rgba(2, 44, 23, 1) 33%,
			rgba(2, 44, 23, 1) 66%,
			rgba(0, 0, 0, 1) 100%
		);
	}
</style>
