<template>
	<view class="shop-content">
		<view class="shop-content-header">
			<u-button text="地图" style="width: 100rpx; margin-right: 20rpx;" shape="square"></u-button>
			<u-search style="flex: 1;" placeholder="请输入关键字" :clearabled="true" :showAction="false" v-model="keyword">
			</u-search>
		</view>
		<v-list class="shop-content-container">
			<v-list-item v-for="(item, index) in infoList" :key="index">
				<navigator class="shop-content-container-item" url="/pages/shop/details">
					<view style="padding: 20rpx; display: flex; flex-direction: row;">
						<view>
							<image :src="item.img" style="width: 160rpx; height: 160rpx;"></image>
						</view>
						<view class="shop-content-container-item-info">
							<text style="margin-bottom: 10rpx;">{{item.title}}</text>
							<text style="margin-bottom: 10rpx;">{{item.address}}</text>
							<text>营业时间{{item.time}}</text>
						</view>
						<view class="shop-content-container-item-address">
							<u-icon name="map-fill" color="#000" size="20"></u-icon>
							<u--text :text="item.instance + 'km'"></u--text>
						</view>
					</view>
				</navigator>
			</v-list-item>
		</v-list>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				keyword: "",
				infoList: [{
					id: 1,
					img: '/static/logo.png',
					title: '皇家码头老火锅',
					address: '重庆火锅 石桥铺',
					time: '9:00~10:00',
					instance: '12.3'
				}, {
					id: 2,
					img: '/static/logo.png',
					title: '皇家码头烧烤',
					address: '重庆烧烤 渝北',
					time: '9:00~10:00',
					instance: '12.5'
				}, {
					id: 3,
					img: '/static/logo.png',
					title: '皇家码头小面',
					address: '重庆小面 解放碑',
					time: '9:00~10:00',
					instance: '10.5'
				}]
			}
		},
		methods: {
			scrolltolower() {
				console.log('触底');
			},
			goDetails(id) {
				console.log('进入详情');
				uni.redirectTo({
					url: "pages/shop/details",
				});
			}
		}
	}
</script>

<style scoped>
	.shop-content {
		padding: 0 20rpx;
		/* background-color: #333333; */
	}

	.shop-content-header {
		display: flex;
	}

	.shop-content-container {
		margin-top: 20rpx;
		display: flex;
		flex-direction: column;
	}

	.shop-content-container-item {
		height: 200rpx;
		/* background-color: #007AFF; */
		margin-bottom: 20rpx;
		border: 1px solid #999999;
		border-radius: 20rpx;
	}

	.shop-content-container-item-info {
		display: flex;
		flex-direction: column;
		margin-left: 20rpx;
	}

	.shop-content-container-item-address {
		display: flex;
		margin-left: 80rpx;
		position: relative;
		bottom: 10rpx;
	}
</style>
