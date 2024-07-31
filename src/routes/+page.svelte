<script>
	import img from '../lib/images/drawers.jpg';
	import profile from '../lib/images/avatar-michelle.jpg';
	import share from '../lib/images/icon-share.svg';
    import share_alt from '../lib/images/icon-share-alt.svg'
	import facebook from '../lib/images/icon-facebook.svg';
	import twitter from '../lib/images/icon-twitter.svg';
	import pinterest from '../lib/images/icon-pinterest.svg';

	let toggle = false;

	const toggleShare = () => {
		toggle = !toggle;
	};
</script>

<div class="container">
	<div class="left">
		<img src={img} alt="" />
	</div>
	<div class="right">
		<h1 class="heading">
			Shift the overall look and feel by adding these wonderful touches to furniture in your home
		</h1>
		<p class="text">
			Ever been in a room and felt like something was missing? Perhaps it felt slightly bare and
			uninviting. I’ve got some simple tips to help you make any room feel complete.
		</p>
		{#if toggle}
			<div class="rel">
				<div class="pop-share-alt">
					<div class="row">
						<div class="txt">SHARE</div>
						<div class="links">
							<img src={facebook} alt="" />
							<img src={twitter} alt="" />
							<img src={pinterest} alt="" />
						</div>
					</div>
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<!-- svelte-ignore a11y-no-static-element-interactions -->
					<div class="right-alter" on:click={toggleShare}>
						<img src={share_alt} alt="" />
					</div>
				</div>
			</div>
		{/if}
		<div class="wrap">
			<div class="left-alt">
				<img class="profile" src={profile} alt="" />
				<div class="text-col">
					<div class="name">Michelle Appleton</div>
					<div class="date">28 Jun 2020</div>
				</div>
			</div>

			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<!-- svelte-ignore a11y-no-static-element-interactions -->
			<div class="right-alt" on:click={toggleShare}>
				{#if toggle}
					<div class="pop-share">
						<div class="row">
							<div class="txt">SHARE</div>
							<div class="links">
								<img src={facebook} alt="" />
								<img src={twitter} alt="" />
								<img src={pinterest} alt="" />
							</div>
						</div>
					</div>
					<div class="triangle"></div>
				{/if}
				<img src={share} alt="" />
			</div>
		</div>
	</div>
</div>

<style>
	.container {
		background-color: white;
		width: 730px;
		height: 280px;
		border-radius: 10px;
		display: flex;
		flex-direction: row;
	}
	.left {
		width: 285px;
		height: 280px;
	}
	.left img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		border-radius: 10px 0 0 10px;
	}
	.right {
		padding: 32px 40px;
	}
	.heading {
		width: 365px;
		color: #48556a;
		font-size: 20px;
		line-height: 28px;
		letter-spacing: 0.25;
		font-weight: bold;
	}
	.text {
		margin-top: 12px;
		width: 365px;
		font-size: 13px;
		font-weight: 500;
		line-height: 20px;
		letter-spacing: 0.12px;
		color: #6e8098;
	}
	.wrap {
		margin-top: 20px;
		width: 365px;
		height: 40px;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
	.left-alt {
		display: flex;
		flex-direction: row;
		gap: 16px;
	}
	.right-alt {
		position: relative;
		width: 32px;
		height: 32px;
		border-radius: 100%;
		background-color: #ecf2f8;
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
	}
	.pop-share {
		position: absolute;
		top: -95px;
		width: 248px;
		height: 55px;
		background-color: #48556a;
		border-radius: 10px;
		display: flex;
		justify-content: center;
		align-items: center;
		transition: 0.3s;
	}
	.rel {
		display: none;
	}
	.triangle {
		position: absolute;
		top: -40px;
		width: 0;
		height: 0;
		border-left: 24px solid transparent;
		border-right: 24px solid transparent;
		border-top: 24px solid #48556a;
		transition: 0.3s;
	}
	.profile {
		width: 40px;
		height: 40px;
		object-fit: cover;
		border-radius: 100%;
	}
	.name {
		font-size: 13px;
		font-weight: bold;
		line-height: 20px;
		letter-spacing: 0.12px;
		color: #48556a;
	}
	.date {
		font-size: 13px;
		font-weight: 500;
		line-height: 20px;
		letter-spacing: 0.12px;
		color: #9daec2;
	}
	.row {
		display: flex;
		flex-direction: row;
		gap: 21px;
	}
	.links {
		display: flex;
		flex-direction: row;
		gap: 16px;
	}
	.txt {
		font-size: 13px;
		font-weight: 500;
		line-height: 20px;
		letter-spacing: 5px;
		color: #9daec2;
	}

	@media only screen and (max-width: 768px) {
		.container {
			width: 327px;
			height: 512px;
			flex-direction: column;
		}
		.left {
			width: 327px;
			height: 200px;
		}
		.left img {
			width: 100%;
			height: 100%;
			object-fit: cover;
			border-radius: 10px 10px 0 0;
		}
		.right {
			padding: 0px 32px;
		}
		.heading {
			margin-top: 36px;
			width: 263px;
			font-size: 16px;
			line-height: 24px;
			letter-spacing: 0.2px;
		}
		.text {
			width: 263px;
		}
		.wrap {
			margin-top: 32px;
			width: 263px;
		}
		.pop-share {
			display: none;
		}
		.triangle {
			display: none;
		}
		.rel {
			position: relative;
			display: block;
		}
		.pop-share-alt {
			z-index: 10;
			padding: 0 32px;
			position: absolute;
			top: 28px;
			left: -32px;
			width: 327px;
			height: 64px;
			background-color: #48556a;
			border-radius: 0 0 10px 10px;
			display: flex;
			justify-content: space-between;
			align-items: center;
			transition: 0.3s;
		}
		.right-alter {
			position: relative;
			width: 32px;
			height: 32px;
			border-radius: 100%;
			background-color: #6E8098;
			display: flex;
			justify-content: center;
			align-items: center;
			cursor: pointer;
		}
	}
</style>
