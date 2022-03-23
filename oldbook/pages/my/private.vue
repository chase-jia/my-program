<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			</view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">隐私政策</view>
			</view>
			<view class="text-area">
				隐私条例
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				syy:{
					url:"../../pages/my/set"
				},
			}
		},
		methods: {
			fanhui(e){
				uni.navigateTo({
					url: e.url
				})
			},
		}
	}
</script>

<style lang="scss">
	.status_bar {
	  height: var(--status-bar-height);
	  width: 100%;
	  
	 }
	.tou{
		position: fixed;
		height: 100upx;
		width: 100%;
		z-index: 5;
		top: 0;
		left: 0;
		background-color: #50d8be;
		box-sizing: border-box;
		.top{
			width: 100%;
			height: 90upx;
			background-color: #50d8be;
			position: relative;
			display: flex;//弹性布局
			align-items: center;
			justify-content: center;
			.jt{
				position: absolute;
				width: 45upx;
				height: 45upx;
				left: 50upx;
				font-size: 45upx;
				
			}
			.zi{
				position: absolute;
				color: #393939;
				font-size: 45upx;
				border-bottom: 6upx #FFFFFF solid;
				font-weight: bold;
			}
		}
	}
</style>

