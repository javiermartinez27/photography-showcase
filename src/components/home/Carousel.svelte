<script lang="ts">

    import { onMount } from "svelte";
    import { activeDescription } from "../../stores";
    
    let container : HTMLElement | undefined = undefined;

    let description : string;

    activeDescription.subscribe(value => {
        description = value;
    })
    
    onMount(() => {
        setMiddleDescription();
        container.addEventListener('wheel', (ev) => {
            ev.preventDefault();  // stop scrolling in another direction
            if (ev.deltaY !== 0)
                container.scrollLeft -= ev.deltaY;
            if (ev.deltaX !== 0)
                container.scrollLeft += ev.deltaX;
        });
    })


    function setMiddleDescription() {
        if (container === undefined) {
            activeDescription.set("");
            return;
        }
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
        let newDescription = closestElement?.firstElementChild?.alt;
        if (newDescription !== undefined) {
            if (newDescription !== description) {
                for (let item of items) {
                    item.children[0].classList.remove('image-centered');
                }
                closestElement.children[0].classList.add('image-centered');
                activeDescription.set(newDescription)
            }
        return
        }
    }

    setInterval(() => {
        setMiddleDescription();
    }, 100)

</script>

<div class="container">
    <section
        id="items-container"
        class="items-container"
        bind:this={container}
    >
        <div style="width: 25%" >
            <div></div> <!-- empty div to prevent item.children[0] from failing -->
        </div>
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
        padding-right: 15rem;

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

    @media screen and (max-width: 650px) {
        .items-container {
            padding-right: 0;
        }
    }
</style>
