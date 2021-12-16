<template>
	<view class="shop-details-content">
		<view class="shop-details-content-header">
			<view class="shop-details-content-header-header">
				<image src="../../static/logo.png" style="width: 150rpx; height: 150rpx;"></image>
				<view style="display: flex; flex-direction: column; margin-left: 30rpx;">
					<text>{{dataInfo.title}}</text>
					<text>{{dataInfo.description}}</text>
					<text style="margin-top: 20rpx;">{{dataInfo.isBusiness}}{{dataInfo.time}}</text>
				</view>
			</view>
			<u-divider style="width: 90%; margin: 0 auto; background-color: #000;"></u-divider>
			<view class="shop-details-content-header-footer">
				<text>{{dataInfo.address}}</text>
				<view style="display: flex;">
					<u-icon name="map-fill" color="#000" size="18"></u-icon>
					<text>{{dataInfo.instance}}km</text>
				</view>
				<view style="display: flex; margin-left: 10rpx;">
					<u-icon name="phone" color="#000" size="18"></u-icon>
					<text>联系商家</text>
				</view>
			</view>
		</view>
		<view class="shop-details-content-middle">
			<text>快捷买单</text>
			<text>
				<u-button text="买单" style="width: 150rpx; height: 50rpx;" shape="circle" @click="onPay"></u-button>
			</text>
		</view>
		<view class="shop-details-content-details">
			<view style="margin-bottom: 20rpx;">商家详情</view>
			<u-row customStyle="margin-bottom: 10px">
				<u-col span="4" v-for="(item,index) in shopDetails">
					<view>
						<image :src="item.src" style="width: 200rpx; height: 200rpx;"></image>
					</view>
				</u-col>
			</u-row>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dataInfo: {
					title: '春风与潮店',
					description: '个性签名个性签名个性签名',
					isBusiness: '营业中',
					time: '9:00~22:00',
					address: '九龙坡区火炬大道13号附11号',
					instance: '12.3'
				},
				shopDetails: [{
						src: '../../static/logo.png'
					},
					{
						src: '../../static/logo.png'
					},
					{
						src: '../../static/logo.png'
					}
				],

			}
		},
		methods: {
			onPay () {
				console.log('123')
				uni.navigateTo({
					url: '/pages/shop/payment'
				})
			}
		}
	}
</script>

<style scoped>
	.shop-details-content {
		padding: 20rpx;
		/* background-color: #555555; */
	}

	.shop-details-content-header {
		border: 1rpx solid #000;
		border-radius: 20rpx;
		height: 300rpx;
	}

	.shop-details-content-header-header {
		display: flex;
		padding: 30rpx;
	}

	.shop-details-content-header-footer {
		font-size: 30rpx;
		display: flex;
		margin-top: 20rpx;
		margin-left: 20rpx;
	}

	.shop-details-content-middle {
		height: 100rpx;
		margin-top: 30rpx;
		border: 1rpx solid #000;
		display: flex;
		justify-content: space-between;
		align-items: center;
		border-radius: 20rpx;
	}

	.shop-details-content-details {
		margin-top: 50rpx;
	}
</style>
