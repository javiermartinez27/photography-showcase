<div class="container">
    <div class="items-container"
        bind:this={container}
    >
        <div style="width: 50%"/>
        <slot></slot>
        <div style="width: 50%"/>
    </div>
</div>

<style>
    .container {
        display: flex;
        overflow: hidden;
        gap: var(--cr-container-gap, 0.5rem);
        justify-content: space-between;
        width: 100%;
    }

    button {
        color: var(--cr-button-color, #000);
        background-color: var(--cr-button-bg-color, white);
        border-color: var(--cr-button-border-color, white);
        border-width: var(--cr-button-border-width, 1px);
        border-radius: var(--cr-button-border-radius, 0.25rem);
        border-style: var(--cr-button-border-style, none);
        padding: var(--cr-button-padding, 1rem);
    }

    .items-container {
        display: flex;
        flex-grow: 1;

        overflow-y: auto;
        overflow-x: auto;

        -webkit-overflow-scrolling: touch;
        -ms-overflow-style: none;  /* IE and Edge */
        scrollbar-width: none;  /* Firefox */
    }

    /* Hide scrollbar for Chrome, Safari and Opera */
    .items-container::-webkit-scrollbar {
        display: none;
    }

    .fake-content {
        height: 2000px;
    }

    :global(.items-container > *) {
        scroll-snap-align: start;
        flex-shrink: 0;
    } 
    
    .items-container::-webkit-scrollbar {
        display: none;
    }
</style>


<script lang="ts">

    import { onMount } from "svelte";
    let container : HTMLElement;

    onMount(() => {
        container.addEventListener('wheel', (ev) => {
            ev.preventDefault();  // stop scrolling in another direction
            if (ev.deltaY !== 0)
                container.scrollLeft -= ev.deltaY;
            if (ev.deltaX !== 0)
                container.scrollLeft += ev.deltaX;
        });
    })
</script>
