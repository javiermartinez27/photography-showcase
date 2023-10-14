<script lang="ts">
	import Carousel from '../components/home/Carousel.svelte';

	import img1 from '$lib/images/img1.jpg';
	import img2 from '$lib/images/img2.jpg';
	import img3 from '$lib/images/img3.jpg';
	import img4 from '$lib/images/img4.jpg';
	import Description from '../components/home/Description.svelte';
	import Picture from '../components/home/Picture.svelte';
	import VerticalLine from '../components/home/VerticalLine.svelte';
	import Header from './Header.svelte';

</script>

<svelte:head>
	<title>Photography</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<Header />
	<VerticalLine/>
	<Carousel >
		<Picture orientation="vertical" src={img1} alt="foto 1 Armored Core VI. Developed by From Software"/>
		<Picture orientation="horizontal" src={img2} alt="foto 2 Cyberpunk 2077. Developed by CD Projekt Red"/>
		<Picture orientation="horizontal" src={img3} alt="foto 3 Cyberpunk 2077. Developed by CD Projekt Red"/>
		<Picture orientation="vertical" src={img4} alt="foto 4 Armored Core VI. Developed by From Software"/>
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

</style>
