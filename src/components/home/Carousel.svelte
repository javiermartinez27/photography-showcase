<script lang="ts">

    import { onMount } from "svelte";
    import { activeDescription } from "../../stores";
    
    let container : HTMLElement = undefined;
    
    onMount(() => {
        activeDescription.set(getMiddleElement())
    })


    function getMiddleElement() {
        if (container === undefined) return;
        const containerRect = container.getBoundingClientRect();
        const containerCenter = containerRect.left + containerRect.width / 2;
        let closestDistance = Infinity;
        let closestElement = null;
        const itemsContainer = document.getElementById('items-container');
        if (!itemsContainer) return;
        const items = itemsContainer.children;
        for (let item of items) {
            const itemRect = item.getBoundingClientRect();
            const itemCenter = itemRect.left + itemRect.width / 2;
            const distance = Math.abs(containerCenter - itemCenter);
            if (distance < closestDistance) {
                closestDistance = distance;
                closestElement = item;
            }
        };
        let description = closestElement?.firstElementChild?.alt;
        if (description !== undefined) return description;
        return items[1]?.firstElementChild?.alt;
    }

    setInterval(() => {
        activeDescription.set(getMiddleElement());
    }, 200)

</script>

<div class="container">
    <section
        id="items-container"
        class="items-container"
        bind:this={container}
    >
        <div style="width: 45%" ></div>
        <slot></slot>
    </section>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        overflow: hidden;
        height: 100vh;
    }


    .items-container {
        display: flex;
        flex-grow: 1;
        align-items: center;

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
