<!-- 分享记录 -->
<template>
	<view class="page_box">
		<!-- 标题栏 -->
		<view class="head_box">
			<view class="nav-box">
				<cu-custom isBack>
					<block slot="backText"><text class="head-title">分享记录</text></block>
				</cu-custom>
			</view>
			<!-- 分类tab -->
			<view class="tab-box x-f">
				<view class="tab-item flex-sub " v-for="(tab, index) in tabsList" :key="tab" @tap="onTab(index)">
					<text class="tab-title" :class="{ 'title-active': tabCurrent == index }">{{ tab }}</text>
					<text class="underline" :class="{ 'underline-active': tabCurrent == index }"></text>
				</view>
			</view>
		</view>

		<view class="content_box">
			<!-- 分享记录列表 -->
			<view class="log-list x-f" v-for="item in 6" :key="item">
				<view class="log-avatar-wrap"><image class="log-avatar" src="/static/imgs/app_icon/icon1.png" mode=""></image></view>

				<view class="item-right">
					<view class="name">旅游顾问-莉莉</view>
					<view class="content x-f">
						<view class="content-img-wrap"><image class="content-img" src="/static/imgs/user/shop_qrcode.png" mode=""></image></view>

						<view class="content-text">通过海报访问了商品“海蓝之谜活颜焕肤精华露”，进入商城</view>
					</view>
					<view class="item-bottom x-bc">
						<view class="time">10月18日 12:00</view>
						<view class="from-text">来自商品分享</view>
					</view>
				</view>
			</view>
		</view>
		<view class="foot_box"></view>
	</view>
</template>

<script>
export default {
	components: {},
	data() {
		return {
			tabCurrent: 0, //默认
			tabsList: ['全部', '名片', '商品', '拼团'] //分类列表
		};
	},
	computed: {},
	onLoad() {},
	methods: {
		// 切换分类
		onTab(index) {
			this.tabCurrent = index;
		}
	}
};
</script>

<style lang="scss">
// nav
.head_box {
	height: 230rpx;
	background: url('http://shopro.7wpp.com/imgs/commission/share_head_bg.png') no-repeat;
	background-size: 100% auto;
	position: relative;
	.nav-box {
		color: #fff;
		font-size: 40rpx;
		/deep/ .cu-back {
			color: #fff;
			font-size: 40rpx;
		}
	}
}
// 分类
.tab-box {
	background-color: #fff;
	border-radius: 20rpx 20rpx 0px 0px;
	position: absolute;
	width: 100%;
	bottom: 0;
	.tab-item {
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		.tab-title {
			color: #666;
			font-weight: 500;
			font-size: 28rpx;
			line-height: 90rpx;
		}
		.title-active {
			color: #333;
		}
		.underline {
			display: block;
			width: 68rpx;
			height: 4rpx;
			background: #fff;
			border-radius: 2rpx;
		}
		.underline-active {
			background: #5e49c3;
			display: block;
			width: 68rpx;
			height: 4rpx;
			border-radius: 2rpx;
		}
	}
}

// 分享记录列表
.log-list {
	background-color: #fff;
	padding: 30rpx;
	margin: 10rpx 0;
	align-items: flex-start;
	.log-avatar-wrap {
		margin-right: 14rpx;
		.log-avatar {
			width: 40rpx;
			height: 40rpx;
			border-radius: 50%;
		}
	}

	.item-right {
		.name {
			font-size: 26rpx;
			font-weight: 500;
			color: #7f7aa5;
			margin-bottom: 30rpx;
		}
		.content {
			background: rgba(241, 241, 241, 0.46);
			border-radius: 2rpx;
			padding: 10rpx;
			margin-bottom: 20rpx;
			.content-img-wrap {
				margin-right: 16rpx;
				width: 80rpx;
				height: 80rpx;
				.content-img {
					width: 80rpx;
					height: 80rpx;
				}
			}

			.content-text {
				font-size: 24rpx;
				font-weight: 500;
				color: #333333;
			}
		}
		.item-bottom {
			.time {
				font-size: 22rpx;
				font-weight: 500;
				color: #c8c8c8;
			}
			.from-text {
				font-size: 22rpx;
				font-weight: 500;
				color: #c8c8c8;
			}
		}
	}
}
</style>
