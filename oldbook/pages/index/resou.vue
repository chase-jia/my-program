<template>
	<view>
		<view class="head_bg">
			<view class="status_bar">
			  <!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/shudan/1.png" mode="" @click="toBack"></image>
				<text class="head_txt">热搜书单</text>
			</view>
		</view>
		<view class="middle">
			<view class="m1">
				<view class="m11">
					TOP2
				</view>
				<view class="m12">
					<image src="../../static/xihuan/1.jpg" mode="" @click="toXiangqing"></image>
					<view class="m13">
						<text>沉默的大多数</text>
					</view>
				</view>
			</view>
			<view class="m2">
				<view class="m21">
					TOP1
				</view>
				<view class="m22">
					<image src="../../static/xihuan/1.jpg" mode="" @click="toXiangqing"></image>
					<view class="m23">
						<text>沉默的大多数</text>
					</view>
				</view>
			</view>
			<view class="m3">
				<view class="m31">
					TOP3
				</view>
				<view class="m32">
					<image src="../../static/xihuan/1.jpg" mode="" @click="toXiangqing"></image>
					<view class="m33">
						<text>沉默的大多数</text>
					</view>
				</view>
			</view>
		</view>
		<view class="bottom">
			<view class="bt" v-for="(item,index) in paihang" :key="index" @click="toXiangqing">
				<text class="bt1">{{item.id}}</text>
				<view class="bt2">
					<view class="bt3">
						<image :src="item.img" mode=""></image>
					</view>
					<view class="bt4">
						<text class="bt5">{{item.name}}</text>
						<text class="bt6">{{item.zuozhe}}</text>
						<text class="bt7">{{item.chuban}}</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			paihang:[
				{
					id:"4",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"5",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"6",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"7",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"8",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"9",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"10",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"11",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
				{
					id:"12",
					img:"../../static/xihuan/1.jpg",
					name:"沉默的大多数",
					zuozhe:"王小波",
					chuban:"人民出版社"
				},
			]	
			}
		},
		methods: {
		toBack(){
			uni.switchTab({
				url:"./index"
			});
		},
		toXiangqing(){
			uni.navigateTo({
				url: "./sesouxq"
			})
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
	height: 80rpx;
	background-color: #50d8be;
	.head{
		height: 100rpx;
		/* #ifdef MP-WEIXIN */
		width: calc(100% - 95px);
		/* #endif */
		/* #ifndef MP-WEIXIN */
		width: 100%;
		/* #endif */
		background-color: #50d8be;
		border-radius: 0 0 100rpx 100rpx;
		image{
			height: 38rpx;
			width: 38rpx;
			margin-left: 50rpx;
			margin-top: 31rpx;
		}
		.head_txt{
			font-size: 45rpx;
			font-weight: bold;
			color: white;
			margin-left: 215rpx;
		}
	}
}
.middle{
	height:400rpx;
	width: 100%;
	padding-left: 20rpx;
	padding-right: 20rpx;
	display: flex;
	margin-top: 195rpx;
	.m1{
		width: 230rpx;
		height: 100%;
		position: relative;
		.m11{
			position: absolute;
			width: 228rpx;
			height: 95rpx;
			bottom: 0;
			background-color: #ffffff;
			border-radius: 30rpx 0 0 0;
			border-top: 2px #808080 solid;
			border-left: 2px #808080 solid;
			font-size: 33rpx;
			font-weight: bold;
			line-height: 95rpx;
			text-align: center;
			color: #50d8be;
			box-shadow: 5rpx 5rpx 10rpx 5rpx #808080
		}
		.m12{
			width: 200rpx;
			height: 260rpx;
			border-radius: 20rpx;
			background-color: #ffffff;
			position: absolute;
			top: 25rpx;
			left: 20rpx;
			image{
				width: 130rpx;
				height: 165rpx;
				margin-left: 35rpx;
				margin-top: 12rpx;
			}
			.m13{
				width: 200rpx;
				background-color: #d9d9d9;
				height: 78rpx;
				border-radius: 0 0 20rpx 20rpx;
				font-size: 24rpx;
				text-align: center;
				line-height: 78rpx;
			}
		}
		
	}
	.m2{
		width: 250rpx;
		height: 100%;
		position: relative;
		.m21{
			position: absolute;
			width: 244rpx;
			height: 140rpx;
			bottom: 0;
			left: 0;
			background-color: #ffffff;
			border-radius: 15rpx 15rpx 0 0;
			border-top: 2px #808080 solid;
			border-right: 2px #808080 solid;
			border-left: 2px #808080 solid;
			font-size: 33rpx;
			font-weight: bold;
			line-height: 140rpx;
			text-align: center;
			color: #50d8be;
			box-shadow: 5rpx 5rpx 10rpx 5rpx #808080
		}
		.m22{
			width: 200rpx;
			height: 260rpx;
			border-radius: 20rpx;
			background-color: #ffffff;
			position: absolute;
			top: -20rpx;
			left: 20rpx;
			image{
				width: 130rpx;
				height: 165rpx;
				margin-left: 35rpx;
				margin-top: 12rpx;
			}
			.m23{
				width: 200rpx;
				background-color: #d9d9d9;
				height: 78rpx;
				border-radius: 0 0 20rpx 20rpx;
				font-size: 24rpx;
				text-align: center;
				line-height: 78rpx;
			}
		}
		
	}
	.m3{
		width: 230rpx;
		height: 100%;
		position: relative;
		.m31{
			position: absolute;
			width: 228rpx;
			height: 55rpx;
			bottom: 0;
			background-color: #ffffff;
			border-radius: 0 20rpx 0 0;
			border-top: 2px #808080 solid;
			border-right: 2px #808080 solid;
			font-size: 33rpx;
			font-weight: bold;
			line-height: 55rpx;
			text-align: center;
			color: #50d8be;
			box-shadow: 5rpx 5rpx 10rpx 5rpx #808080
		}
		.m32{
			width: 200rpx;
			height: 260rpx;
			border-radius: 20rpx;
			background-color: #ffffff;
			position: absolute;
			top: 44rpx;
			left: 20rpx;
			image{
				width: 130rpx;
				height: 165rpx;
				margin-left: 35rpx;
				margin-top: 25rpx;
			}
			.m33{
				width: 200rpx;
				background-color: #d9d9d9;
				height: 78rpx;
				border-radius: 0 0 20rpx 20rpx;
				font-size: 24rpx;
				text-align: center;
				line-height: 78rpx;
			}
		}
		
	}
}
.bottom{
	padding-top: 52rpx;
	.bt{
		width: 660rpx;
		height: 200rpx;
		margin: 30rpx 45rpx 30rpx 45rpx;
		position: relative;
		.bt1{
			font-size: 50rpx;
			line-height: 200rpx;
			font-weight: bold;
			font-style:oblique;
			color: #50d8be;
		}
		.bt2{
			position: absolute;
			background-color: #ffffff;
			top: 0;
			right: 0;
			width: 575rpx;
			height: 196rpx;
			border-radius: 20rpx;
			border: 2rpx #808080 solid;
			box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
			.bt3{
				width: 200rpx;
				height: 196rpx;
				border-radius: 20rpx 0 0 20rpx;
				border: 2rpx #808080 solid;
				box-shadow: 3rpx 3rpx 10rpx 3rpx #808080;
				image{
					width: 140rpx;
					height: 190rpx;
					margin-left: 30rpx;
				}
			}
			.bt4{
				display: flex;
				box-sizing: border-box;
				position: absolute;
				left: 235rpx;
				top: 0;
				flex-direction: column;
				.bt5{
					width: 100%;
					height: 54rpx;
					font-size: 30rpx;
					line-height: 54rpx;
					color: #b6b8ba;
				}
				.bt6{
					width: 100%;
					height: 66rpx;
					font-size: 25rpx;
					line-height: 66rpx;
					color: #b6b8ba;
				}
				.bt7{
					width: 100%;
					height: 76rpx;
					font-size: 23rpx;
					line-height: 76rpx;
					color: #b6b8ba;
				}
			}
		}
	}
}
</style>
