<template lang="">
	<div>
		<ul class="actor-grid">
			<Actor
				v-for="character in characters"
				v-bind:characterInfo="character"
				v-bind:key="character"
			></Actor>
			<!-- v-bind:characterInfo is the prop to be passed to the child, that's why its name is unique -->
			<!-- v-bind:key should be char_id but it aint working -->
		</ul>
		<!-- {{ characters.length }} -->
	</div>
</template>
<script>
	import Actor from "./Actor";

	export default {
		name: "ActorList",
		components: {
			Actor
		},
		props: ["characters"]
	};
</script>
<style scoped>
	.actor-grid {
		width: 80%;
		margin: 75px auto;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 20px;
	}
</style>
