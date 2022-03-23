<template>
	<view class="content">
		<view class="">
			<view class="status_bar">
				<!-- 这里是状态栏 -->
			</view>
		</view>
		<view class="mainbody" v-show="issure" >
			<view class="mainbrain" >
				<button type="default" @click="replace">确认</button>
				<button type="default" @click="replace1">取消</button>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
				
				
			}
		},
		props: {
			issure: {
				type: Boolean,
				default: false
			}
			
		
		},
		onLoad() {

		},
		methods: {
			replace() {
          this.$emit("replace",this.issure);
			},
			replace1() {
          this.$emit("replace1",this.issure); 
			}
		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.status_bar {
		height: var(--status-bar-height);
		width: 100%;
	}

	.mainbody {
		width: 100%;
		height: 400rpx;
		position: fixed;
		top: 300rpx;
		z-index: 100;
		display: flex;
		justify-content: space-around;
		align-items: center;

		.mainbrain {
			border-radius: 5rpx;
			width: 80%;
			height: 200rpx;
			background-color: #8a8a8a;
			opacity: 0.8;
			display: flex;
			justify-content: space-around;
			align-items: center;

			button {
				width: 180rpx;
				height: 60rpx;
				text-align: center;
				line-height: 60rpx;
			}

		}
	}
</style>
