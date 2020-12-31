<template lang="">
	<div>
		<!-- Breaking Bad -->
		<Header></Header>
		<Search v-on:wordChange="onWordChange"></Search>
		<ActorList v-bind:characters="actorInfo"></ActorList>
		<!-- characters is the name of the property we want to show up in the child component -->
		<!-- {{ actorInfo.length }} -->
		<Actor></Actor>
	</div>
</template>
<script>
	import Header from "./components/Header";
	import Search from "./components/Search";
	import ActorList from "./components/ActorList";
	import Actor from "./components/Actor";
	import axios from "axios";

	export default {
		name: "App",
		data: function() {
			return { actorInfo: [] };
		},
		components: {
			Header,
			Search,
			ActorList,
			Actor
		},
		mounted() {
			axios
				.get("https://www.breakingbadapi.com/api/characters", {})
				.then((response) => {
					this.actorInfo = response.data;
					// this.datas = response.data;
					// console.log(response.data);
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
		font-size: 15px;
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
