<template>
	<view class="content">
		<view class="content-image">
			<image class="content-image-logo" src="/static/logo.png"></image>
		</view>
		<view class="content-area">
			<u-row justify="center">
				<u-col span="3" v-for="(item,index) in viewInfoList">
					<navigator class="content-area-item" :url="item.url">
						<image :src="item.img" style="width: 150rpx; height: 60px;" />
						<text>{{item.title}}</text>
					</navigator>
				</u-col>
			</u-row>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				viewInfoList: [{
						img: "/static/logo.png",
						title: "领取优惠",
						url: "/pages/lottery/lottery"
					},
					{
						img: "/static/logo.png",
						title: "我的XXX币",
						url: "/pages/shop/details"
					},
					{
						img: "/static/logo.png",
						title: "使用XX币",
						url: "/pages/lottery/lottery"
					},
					{
						img: "/static/logo.png",
						title: "商家入驻",
						url: "/pages/lottery/lottery"
					}
				]
			}
		},
		onLoad() {

		},
		methods: {
			goTo(url) {
				//路由跳转
				console.log('路由跳转', url);
				uni.navigateTo({
					url
				});
			}
		}
	}
</script>

<style>
	.content {
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		/* background-color: #000; */
	}

	.content-image {
		height: 70%;
		width: 100%;
		/* background-color: #333333; */
	}

	.content-image-logo {
		height: 900rpx;
		width: 650rpx;
		margin: 50rpx;
	}

	.content-area {
		height: 30%;
		margin-top: 30px;
		width: 100%;
		/* background-color: #4CD964; */
	}

	.content-area-item {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
</style>
