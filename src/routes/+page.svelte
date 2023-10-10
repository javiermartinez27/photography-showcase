<script lang="ts">
	import Carousel from '../components/home/Carousel.svelte';

	import img1 from '$lib/images/img1.jpg';
	import img2 from '$lib/images/img2.jpg';
	import img3 from '$lib/images/img3.jpg';
	import img4 from '$lib/images/img4.jpg';
	import Description from '../components/home/Description.svelte';

</script>

<svelte:head>
	<title>Photography</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<Carousel >
		<div class="horizontal-picture">
			<img src={img1} alt="Armored Core VI. Developed by From Software" width="90%">
		</div>
		<div class="horizontal-picture">
			<img src={img2} alt="Cyberpunk 2077. Developed by CD Projekt Red" width="80%">
		</div>
		<div class="horizontal-picture">
			<img src={img3} alt="Cyberpunk 2077. Developed by CD Projekt Red" width="90%">
		</div>
		<div class="horizontal-picture">
			<img src={img4} alt="Armored Core VI. Developed by From Software" width="75%">
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

	.horizontal-picture {
		width: 60%;
	}

	@media screen and (max-width: 768px) {
		.horizontal-picture {
			width: 90%;
		}
	}

</style>
