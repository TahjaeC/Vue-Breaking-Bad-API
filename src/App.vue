<template lang="">
	<div>
		<!-- Breaking Bad -->
		<Header></Header>
		<Search></Search>
	</div>
</template>
<script>
	import Header from "./components/Header";
	import Search from "./components/Search";
	export default {
		name: "App",
		components: {
			Header,
			Search
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
