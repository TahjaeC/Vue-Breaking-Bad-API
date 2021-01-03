<template lang="">
	<div>
		<li>
			<div class="card">
				<img v-bind:src="characterInfo.img" alt="Avatar" style="width:100%" />
				<div class="container">
					<h2>{{ characterInfo.name }}</h2>
					<ul>
						<li class="item">
							<span>Occupation:</span> {{ characterInfo.occupation }}
						</li>
						<li class="item">
							<span>Nickname:</span> {{ characterInfo.nickname }}
						</li>
						<li class="item">
							<span>Status:</span> {{ characterInfo.status }}
						</li>
						<li class="item">
							<span>Portrayed By:</span> {{ characterInfo.portrayed }}
						</li>
						<li class="item">
							<span>Season Appearance(s):</span> {{ characterInfo.appearance }}
						</li>
					</ul>
				</div>
			</div>
		</li>
	</div>
</template>
<script>
	export default {
		name: "Actor",
		props: ["characterInfo"]
	};
</script>
<style scoped>
	li {
		list-style: none;
	}
	.item {
		margin: 10px auto;
		color: white;
	}
	span {
		font-size: 1rem;
		font-weight: bold;
	}
	img {
		height: 500px;
		width: auto;
	}
	.card {
		/* Add shadows to create the "card" effect */
		box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
		transition: 0.3s;
		height: 750px;
		background-color: rgb(19, 17, 15);
	}

	/* Add some padding inside the card container */
	.container {
		padding: 10px 16px;
	}
</style>
