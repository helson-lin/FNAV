<template>
	<div class="slider">
		<div v-for="(item, index) in list" :key="index" class="slider-item">
			{{ item.name }}
		</div>
		<FTab />
	</div>
</template>
<script>
import FTab from './FTab.vue'
export default {
	name: `Slider`,
	components: { FTab },
	data() {
		return {
			list: [{ name: '分类' }],
		}
	},
}
</script>
<style lang="scss" scoped>
.slider {
	width: 224px;
	height: 100%;
	box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
	@include background_color('bc_color');
	display: flex;
	flex-direction: column;
	align-items: center;
	.slider-item {
		margin-bottom: 20px;
	}
}
</style>
