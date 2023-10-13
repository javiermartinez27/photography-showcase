<script>

</script>

<svelte:head>
	<link href="https://fonts.googleapis.com/css2?family=Rubik+Microbe&display=swap" rel='stylesheet' type='text/css'>
</svelte:head>

<header>
	<div class="logo">JMPS</div>
	<div class="games-list">list</div>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		position: absolute;
		top: 0;
		width: 100%;
	}

	.logo {
		font-family: 'Rubik Microbe', sans-serif;
		font-size: 2.5rem;
		margin-left: -30px;
		color: black;
		transform: rotate(90deg);
		margin-top: 3rem
	}

	.games-list {
		display: flex;
		flex-direction: column;
		justify-content: center;
		margin: 1.5rem;
		border: solid 1.5px black;
		padding: 0 2rem;
		height: 2rem;
	}

</style>
