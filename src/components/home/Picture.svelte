<script lang="ts">
	import { onMount } from "svelte";


    export let orientation : string;
    export let src : string;
    export let alt : string;

    let className : string;
    let width : string;

    onMount(() => {
        if (orientation === 'horizontal') {
            className = 'horizontal-pic-container';
        } else {
            className = 'vertical-pic-container';
        }
    })

	function randomPadding() {
        return Math.floor(Math.random() * 6).toString() + 'rem';
    }

</script>

<div class={className} style="padding-bottom: {randomPadding()};">
    <img class="carousel-image" {src} {alt} {width}>
</div>

<style>
    .horizontal-pic-container {
		display: flex;
		justify-content: center;
		width: 75%;
		max-height: 85%;
	}

    .horizontal-pic-container * {
        width: 80%;
        object-fit: contain;
    }

	.vertical-pic-container {
		display: flex;
		justify-content: center;
		width: 55%;
		max-height: 85%;
	}

    .vertical-pic-container * {
        width: 90%;
        object-fit: contain;
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