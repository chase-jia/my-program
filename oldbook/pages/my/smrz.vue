<template>
	<view>
		<view class="tou">
			<view class="status_bar">
			</view>
			<view class="top">
				<image src="../../static/shu/jt1.png" mode="" class="jt" v-model="syy" @click="fanhui(syy)"></image>
				<view class="zi">实名认证</view>
			</view>
			<view class="yy">请填写您本人真实姓名和身份证号码</view>
			<view class="put">
				<input type="" value="" placeholder="请输入您的真实姓名" placeholder-style="color: #6e7070;font-size: 20upx;" style="text-align: left;cursor:100upx"/>
				<input type="" value="" placeholder="请输入您的身份证号码" placeholder-style="color: #6e7070;font-size: 20upx;" style="text-align: left;cursor:100upx"/>
				<button class="_o" type="default">提交资料</button>
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
	.yy{
		display: flex;
		box-sizing: border-box;
		font-size:40upx;
		color: #4a4a4a;
		margin: 20upx;
		background-color: #d9d9d9;
		padding-left: 30upx;
	}
	.put{
		margin-top: 70upx;
		input{
			font-size: 50upx;
			color: #9e9e9e;
			margin: 0 auto;
			padding-left: 50upx;
			border: 6upx #9e9e9e solid;
			margin-top: -6upx;
		}
		._o{
			
		}
	}
</style>
