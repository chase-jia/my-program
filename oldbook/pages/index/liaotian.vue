<template>
	<view>
		<view class="head_bg">
			<view class="status_bar">
			  <!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/shudan/1.png" mode="" @click="toBack"></image>
				<text class="head_txt">老笔斋的老猫</text>
			</view>
		</view>
		<view class="kuang">
			<view class="k1" v-for="(item,index) in show" v-show="true">
				<text class="k11">{{item}}</text>
				<image src="../../static/bookcircle/people1.png" mode=""></image>
			</view>
		</view>
		<view class="bottom">
			<input class="bt1" type="text" value="" v-model="tamade" />
			<view class="bt2">
				<text @click="push">发送</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:[],
				arr:[],
					// shuju:"",
				changeitem:true,
				tamade:""
			}	
		},
		methods: {
			toBack(){
				uni.navigateBack({
					url:"./index"
				});
			},
			push(){
				this.arr=this.tamade;
				// this.changeitem=!this.changeitem;
				this.show.push(this.arr);
				this.tamade="";
				console.log(this.show);
				// this.changeitem=!this.changeitem;
			}
		}
	}
</script>

<style lang="scss">
.status_bar {
		height: var(--status-bar-height);
		width: 100%;
}
.head_bg{
	z-index: 100;
	position: fixed;
	left: 0;
	top: 0;
	width: 100%;
	background-color: #50d8be;
	.head{
		height: 100rpx;
		/* #ifdef MP-WEIXIN */
		width: calc(100% - 95px);
		/* #endif */
		/* #ifndef MP-WEIXIN */
		width: 100%;
		/* #endif */
		image{
			height: 38rpx;
			width: 38rpx;
			margin-left: 50rpx;
			margin-top: 31rpx;
		}
		.head_txt{
			font-size: 45rpx;
			color: white;
			margin-left: 25rpx;
		}
	}
}
.kuang{
	margin-top: 100rpx;
	width: 100%;
	padding-top: 50rpx;
	.k1{
		position: relative;
		margin-right: 15rpx;
		margin-top: 30rpx;
		width: 700rpx;
		height: 80rpx;
		display: flex;
		image{
			position: absolute;
			right: 0;
			top: 0rpx;
			width: 60rpx;
			height: 60rpx;
			border-radius: 30rpx;
		}
		.k11{
			position: absolute;
			right: 65rpx;
			width: 300rpx;
			height: 80rpx;
			background-color: #50d8be;
			text-align: center;
			line-height: 80rpx;
			color: white;
			font-size: 25rpx;
			border-radius: 20rpx;
			
		}
	}
	
}
.bottom{
	z-index: 100;
	position: fixed;
	left: 0;
	bottom: 0;
	height: 100rpx;
	width: 100%;
	background-color: #808080;
	display: flex;
	.bt1{
		margin-left: 20rpx;
		margin-top: 10rpx;
		height: 80rpx;
		width: 580rpx;
		border-radius: 20rpx;
		background-color: #ffffff;
	}
	.bt2{
		margin-top: 10rpx;
		margin-left: 10rpx;
		width: 120rpx;
		height: 80rpx;
		border-radius: 20rpx;
		background-color: #50d8be;
		font-size: 35rpx;
		color: white;
		text-align: center;
		line-height: 80rpx;
		
	}
}
</style>
