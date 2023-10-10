<script lang="ts">
	import Carousel from '../components/home/Carousel.svelte';

	import img1 from '$lib/images/img1.jpg';
	import img2 from '$lib/images/img2.jpg';
	import img3 from '$lib/images/img3.jpg';
	import img4 from '$lib/images/img4.jpg';
	import Description from '../components/home/Description.svelte';

	function randomPadding() {
        return Math.floor(Math.random() * 6).toString() + 'rem';
    }

</script>

<svelte:head>
	<title>Photography</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<Carousel >
		<div class="vertical-pic-container" style="padding-bottom: {randomPadding()};">
			<img src={img1} alt="foto 1 Armored Core VI. Developed by From Software" width="55%">
		</div>
		<div class="horizontal-pic-container" style="padding-bottom: {randomPadding()};">
			<img src={img2} alt="foto 2 Cyberpunk 2077. Developed by CD Projekt Red" width="70%">
		</div>
		<div class="horizontal-pic-container" style="padding-bottom: {randomPadding()};">
			<img src={img3} alt="foto 3 Cyberpunk 2077. Developed by CD Projekt Red" width="70%">
		</div>
		<div class="vertical-pic-container" style="padding-bottom: {randomPadding()};">
			<img src={img4} alt="foto 4 Armored Core VI. Developed by From Software" width="55%">
		</div>
	</Carousel>

	<Description/>
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

	.horizontal-pic-container {
		display: flex;
		justify-content: center;
		width: 75%;
		max-height: 85%;
	}

	.vertical-pic-container {
		display: flex;
		justify-content: center;
		width: 55%;
		max-height: 85%;
	}

	@media screen and (max-width: 650px) {
		.horizontal-pic-container {
			width: 90%;
		}

		.horizontal-pic-container * {
			width: 80%;
		}

		.vertical-pic-container {
			width: 75%;
		}

		.vertical-pic-container * {
			width: 90%;
		}
	}

</style>
