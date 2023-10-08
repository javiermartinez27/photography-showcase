<script lang="ts">
	import Carousel from '../components/home/MainCarousel.svelte';

	import img1 from '$lib/images/img1.jpg';
	import img2 from '$lib/images/img2.jpg';
	import img3 from '$lib/images/img3.jpg';
	import img4 from '$lib/images/img4.jpg';
	import Description from '../components/home/Description.svelte';

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
		<!-- <span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</span>

		to your new<br />SvelteKit app -->
		<Carousel >
			<div style="width: 50%">
				<img src={img1} alt="Armored Core VI. Developed by From Software" width="90%">
			</div>
			<div style="width: 50%">
				<img src={img2} alt="Cyberpunk 2077. Developed by CD Projekt Red" width="80%">
			</div>
			<div style="width: 50%">
				<img src={img3} alt="Cyberpunk 2077. Developed by CD Projekt Red" width="90%">
			</div>
			<div style="width: 50%">
				<img src={img4} alt="Armored Core VI. Developed by From Software" width="75%">
			</div>
		</Carousel>

		<Description/>

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
		flex: 1;
		height: 100%;
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
