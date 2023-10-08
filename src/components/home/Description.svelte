<script lang="ts">
    import { mainMenuActiveDescription } from "../../stores";
    let description : string;

    mainMenuActiveDescription.subscribe(value => {
        description = value;
    })
</script>

<section>
    <p>{description}</p>
</section>

<style>
    section {
        border: 2px solid black;
        position: fixed;
        bottom: 30px;
        width: 20em;
        height: 8em;
        text-align: center;
    }
</style>
