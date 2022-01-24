<template>
	<div class="home" :class="themeClass">
		<Slider />
		<div class="container"></div>
	</div>
</template>

<script>
import Slider from '../../components/Slider.vue'
export default {
	name: 'HomePage',
	components: { Slider },
	data() {
		return {
			theme: 'red',
		}
	},
	computed: {
		themeClass() {
			return `theme-${this.theme}`
		},
	},
}
</script>
<style lang="scss" scoped>
.home {
	height: 100vh;
	display: flex;
	.container {
		flex: 1;
		height: 100%;
		padding: 0 200px;
		box-sizing: border-box;
		@include background_color('bcc_color');
		img {
			width: 200px;
			height: 100px;
			display: inline-block;
			&:hover {
				content: url('https://pic.kblue.site/img/202201211447091.jpg');
			}
		}
		.img-li {
			width: 300px;
			height: 240px;
			background: url('https://pic.kblue.site/img/202201211447091.jpg'),
				radial-gradient(rgba(0, 255, 0, 0.8), black),
				repeating-linear-gradient(
					transparent 0,
					rgba(0, 0, 0, 0.2) 3px,
					transparent 6px
				);
			background-size: cover;
			background-blend-mode: overlay;
		}
	}
}
</style>
