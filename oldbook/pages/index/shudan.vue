<template>
	<view>
		<view class="head_bg">
			<view class="status_bar">
			  <!-- 这里是状态栏 -->
			</view>
			<view class="head">
				<image src="../../static/shudan/1.png" mode="" @click="toBack"></image>
				<text class="head_txt">书单推荐</text>
			</view>
		</view>
		<view class="tj">
			<view class="tuijian" v-for="(item,index) in list" :key="index" @click="toXiangqing">
				<view class="tj1">
					<image :src="item.img1" mode=""></image>
				</view>
				<view class="tj2">
					<view class="tj21">
						<text class="tj211">{{item.name}}</text>
						<text class="tj212">{{item.num1}}人推荐了{{item.num2}}本书</text>
					</view>
					<view class="tj22">
						<view class="tj221">
							<view class="tj2211">
								<image :src="item.img2" mode=""></image>
							</view>
							<view class="tj2212">
								<image :src="item.img3" mode=""></image>
							</view>
							<view class="tj2213">
								<image :src="item.img4" mode=""></image>
							</view>
						</view>
						<text class="tj222">等{{item.num3}}人收藏</text>
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
			list:[
				{
					img1:"../../static/shudan/3.jpg",
					name:"那些有趣的历史",
					num1:"23",
					num2:"27",
					num3:"213",
					img2:"../../static/shudan/4.jpg",
					img3:"../../static/shudan/5.jpg",
					img4:"../../static/shudan/6.jpg"
				},{
					img1:"../../static/shudan/3.jpg",
					name:"那些有趣的历史",
					num1:"23",
					num2:"27",
					num3:"213",
					img2:"../../static/shudan/4.jpg",
					img3:"../../static/shudan/5.jpg",
					img4:"../../static/shudan/6.jpg"
				},{
					img1:"../../static/shudan/3.jpg",
					name:"那些有趣的历史",
					num1:"23",
					num2:"27",
					num3:"213",
					img2:"../../static/shudan/4.jpg",
					img3:"../../static/shudan/5.jpg",
					img4:"../../static/shudan/6.jpg"
				},{
					img1:"../../static/shudan/3.jpg",
					name:"那些有趣的历史",
					num1:"23",
					num2:"27",
					num3:"213",
					img2:"../../static/shudan/4.jpg",
					img3:"../../static/shudan/5.jpg",
					img4:"../../static/shudan/6.jpg"
				},{
					img1:"../../static/shudan/3.jpg",
					name:"那些有趣的历史",
					num1:"23",
					num2:"27",
					num3:"213",
					img2:"../../static/shudan/4.jpg",
					img3:"../../static/shudan/5.jpg",
					img4:"../../static/shudan/6.jpg"
				},{
					img1:"../../static/shudan/3.jpg",
					name:"那些有趣的历史",
					num1:"23",
					num2:"27",
					num3:"213",
					img2:"../../static/shudan/4.jpg",
					img3:"../../static/shudan/5.jpg",
					img4:"../../static/shudan/6.jpg"
				},{
					img1:"../../static/shudan/3.jpg",
					name:"那些有趣的历史",
					num1:"23",
					num2:"27",
					num3:"213",
					img2:"../../static/shudan/4.jpg",
					img3:"../../static/shudan/5.jpg",
					img4:"../../static/shudan/6.jpg"
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
				url: "./shudanxq"
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
	background-color: #50d8be;
	border-radius: 0 0 100rpx 100rpx;
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
			font-weight: bold;
			color: white;
			margin-left: 215rpx;
		}
	}
}
.tj{
	padding-top: 150rpx;
	.tuijian{
		width: 640rpx;
		height: 480rpx;
		background-color: #ffffff;
		margin: 35rpx 55rpx 0rpx 55rpx;
		border-radius: 20rpx;
		box-shadow: 5rpx 5rpx 10rpx 5rpx #808080;
		.tj1{
			width: 634rpx;
			height: 355rpx;
			margin: 0 auto;
			border-radius: 20rpx 20rpx 0 0;
			image{
				width: 634rpx;
				height: 355rpx;
				border-radius: 20rpx 20rpx 0 0;
			}
		}
		.tj2{
			width: 640rpx;
			height: 125rpx;
			border-radius: 0 0 20rpx 20rpx;
			display: flex;
			position: relative;
			.tj21{
				display: flex;
				flex-direction: column;
				.tj211{
					font-size: 20rpx;
					margin-top: 20rpx;
					margin-left: 30rpx;
				}
				.tj212{
					font-size: 15rpx;
					margin-top: 20rpx;
					margin-left: 30rpx;
					color: #caced2;
				}
			}
			.tj22{
				width: 350rpx;
				height: 100%;
				position: absolute;
				right: 0;
				display: flex;
				.tj221{
					width: 184rpx;
					height: 100%;
					// display: flex;
					position: absolute;
					.tj2211{
						position: absolute;
						left: 0;
						top: 25rpx;
						image{
							width: 70rpx;
							height: 70rpx;
							border-radius: 35rpx;
						}
					}
					.tj2212{
						// margin-left: 50rpx;
						position: absolute;
						left: 50rpx;
						top: 25rpx;
						image{
							width: 70rpx;
							height: 70rpx;
							border-radius: 35rpx;
						}
					}
					.tj2213{
						position: absolute;
						left: 100rpx;
						top: 25rpx;
						image{
							width: 70rpx;
							height: 70rpx;
							border-radius: 35rpx;
						}
					}
					
				}
				.tj222{
					position: absolute;
					width: 166rpx;
					height: 100%;
					left: 180rpx;
					top: 50rpx;
					font-size: 23rpx;
					color: #caced2;
				}
			}
		}
	}
}
</style>
