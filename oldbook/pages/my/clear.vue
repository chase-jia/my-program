<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			</view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">清除缓存</view>
			</view>
			<u-popup v-model="show" mode="center">
				<view style="width: 400upx;height: 100upx;font-size: 50upx;font-weight: bold;
				padding:15upx 70upx;">已清除缓存</view>
			</u-popup>
			<u-button @click="show = true" style="margin-top: 100upx;color: 50d8be;
			height: 150upx;font-size: 50upx;font-weight: bold;">点击清除缓存</u-button>
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
				show: false
			}
		},
		methods: {
			fanhui(e){
				uni.navigateTo({
					url: e.url
				})
			},
			qchc(){
				
			}
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