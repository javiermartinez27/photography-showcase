<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import Carousel from '../components/home/Carousel.svelte';

	import img1 from '$lib/images/img1.jpg';
	import img2 from '$lib/images/img2.jpg';
	import img3 from '$lib/images/img3.jpg';
	import img4 from '$lib/images/img4.jpg';

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>
		<!-- <span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</span>

		to your new<br />SvelteKit app -->
		<Carousel>
			<div style="width: 50%">
				<img src={img1} alt="" width="200">
				<p>@a</p>
			</div>
			<div style="width: 50%">
				<img src={img2} alt="" width="200">
				<p>@a</p>
			</div>
			<div style="width: 50%">
				<img src={img3} alt="" width="200">
				<p>@a</p>
			</div>
			<div style="width: 50%">
				<img src={img4} alt="" width="200">
				<p>@a</p>
			</div>
		</Carousel>
	</h1>

	<!-- <h2>
		try editing <strong>src/routes/+page.svelte</strong>
	</h2>

	<Counter /> -->
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
