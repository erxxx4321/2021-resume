<template>
	<Resume />
</template>

<script>
	import Resume from "./components/Resume.vue";

	export default {
		name: "App",
		components: {
			Resume,
		},
	};
</script>

<style>
	* {
		box-sizing: border-box;
		line-height: 1.4;
		margin: 0;
		padding: 0;
		font-family: "Roboto Slab", serif;
	}

	:root {
		--primary: #576d7b;
		--secondary: #f5f5f5;
		--dark: #c6c1c1;
	}

	@media screen and (-webkit-min-device-pixel-ratio: 0) {
		select,
		textarea,
		input {
			font-size: 16px;
			background: #fff;
		}
	}
</style>
