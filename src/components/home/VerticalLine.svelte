<div class="circle">
    <div class="transparent-circle"></div>
</div>
<div class="line"></div>

<style>
    	.circle {
		position: absolute;
		top: 25%; left: 50%;
		transform: translate(-50%, -50%);
		width: 35px;
		height: 35px;
		background-color: black;
		border-radius: 100%;
	}
	.transparent-circle {
		position: absolute;
		top: 50%; left: 50%;
		transform: translate(-50%, -50%);
		width: 32px;
		height: 32px;
		background-color: var(--color-bg-1);
		border-radius: 100%;
	}
	.line {
		position: absolute;
		top: 50%; left: 50%;
		transform: translate(-50%, -50%);
		width: 1.5px;
		height: 100%;
		background-color: black;
		z-index: -99;
	}
</style>