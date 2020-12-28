<template lang="">
	<div>
		<div class="header-container">
			<img src="../img/logo.svg" alt="Breaking Bad Logo" />
		</div>
	</div>
</template>
<script>
	export default {
		name: "Header"
	};
</script>
<style scoped>
	.header-container {
		display: flex;
		justify-content: start;
	}

	img {
		padding-left: 40px;
		padding-top: 40px;
		width: 190px;
	}
</style>
