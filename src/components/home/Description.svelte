<script lang="ts">
    import { fade } from "svelte/transition";

    import { activeDescription } from "../../stores";

    let description : string;

    activeDescription.subscribe(value => {
        description = value;
    })
</script>

<section>
    {#key description}
        <p in:fade>{description}</p>
    {/key}
</section>

<style>
    section {
        border: 1.5px solid black;
        position: fixed;
        bottom: 30px;
        width: 20em;
        height: 8em;
        text-align: center;
        background-color: var(--color-bg-1);
    }
</style>
