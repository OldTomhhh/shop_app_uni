<template>
	<view class="lottery-content">
		<u-notice-bar class="lottery-content-bar" :text="text1"></u-notice-bar>
		<view class="lottery-content-main">
			<u-grid :border="true">
				<u-grid-item :customStyle="{width:220+'rpx',height:220+'rpx'}" v-for="(item, index) in swiperList"
					:index="index" :key="index">
					<u-icon :customStyle="{paddingTop:20+'rpx'}" :name="item" :size="22"></u-icon>
					<text class="grid-text">{{ '币 30' }}</text>
				</u-grid-item>
			</u-grid>
			<text style="display: flex; 
				justify-content: center;
				margin-top: 20rpx;">
				您今天还有1次抽奖计划22
			</text>
			<u-button @click="onLottery">点击抽奖</u-button>
		</view>
		<view class="lottery-content-footer">
			<u-divider text="中奖历史"></u-divider>
			<view class="lottery-content-footer-item" v-for="(item,index) in history">
				<view>
					<!-- <image src=></image> -->
					<text>{{item.title}}</text>
				</view>
				<view>
					{{item.time}}
				</view>
			</view>
		</view>
		<u-modal :show="show" :title="resultInfo.title" :content='resultInfo.content' @confirm="confirmResult">
		</u-modal>
	</view>
</template>

<script>
	import moment from 'moment';
	export default {
		data() {
			return {
				text1: "何庆均 中得了 iPhone 一台     xxxxx 中得了 优惠券一张",
				swiperList: ['integral', 'kefu-ermai', 'coupon', 'gift', 'scan', 'pause-circle', 'wifi', 'email', 'list'],
				history: [{
					img: '',
					title: '币 30',
					time: moment(new Date()).format('YYYY-MM-DD HH:mm')
				}, {
					img: '',
					title: '币 20',
					time: moment(new Date()).format('YYYY-MM-DD HH:mm')
				}],
				resultInfo: {
					title: "",
					content: ""
				},
				show: false
			}
		},
		methods: {
			onLottery() {
				console.log('点击抽奖');
				if (true) {
					this.$nextTick(() => {
						this.resultInfo.title = '恭喜您获得iPhone xxx';
						this.resultInfo.content = '奖品若是实物将以兑换券的形式放入您的卡包.若是积分，请直接在“我的积分”查询。'
						this.show = true;
					});
				} else {
					this.$nextTick(() => {
						// this.resultInfo.title = '恭喜您获得iPhone xxx';
						this.resultInfo.content = '对不起，您没有中得任何奖品哦'
						this.show = true;
					});
				}
			},
			confirmResult() {
				this.show = false;
			}
		}
	}
</script>

<style scoped>
	.lottery-content {
		height: 100%;
		width: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		/* background-color: #555555; */
	}

	.lottery-content-bar {
		width: 90%;
	}

	.lottery-content-main {
		margin-top: 120rpx;
		width: 90%;
		/* height: 1000rpx; */
		/* background-color: #007AFF; */
		/* 		display: flex;
		justify-content: center;
		align-items: center; */
	}

	.lottery-content-footer {
		position: absolute;
		bottom: 180rpx;
		width: 90%;
	}

	.lottery-content-footer-item {
		display: flex;
		justify-content: space-between;
	}

	.grid-text {
		font-size: 14px;
		/* color: #909399; */
		padding: 10rpx 0 20rpx 0rpx;
		/* #ifndef APP-PLUS */
		box-sizing: border-box;
		/* #endif */
	}
</style>
