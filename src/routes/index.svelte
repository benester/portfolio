<script>
	const layers = [ 1, 2, 3, 4, 5, 6, 7];

	let y;
	let x;
</script>

<svelte:window bind:scrollY={y} bind:innerWidth={x}/>
{#if x > 900}
<div class="parallax-container" style="width:{x}px">
	{#each layers as layer}
		<img
			style="transform: translate(0,{-y * layer / (layers.length - 1)}px)"
			src="layerdForest{layer}.png"
			alt="parallax layer {layer}"
		>
	{/each}
</div>
{:else}
<div class="parallax-container-small" style="width:{x}px">
	{#each layers as layer}
		<img
			style="transform: translate(0,{-y * layer / (layers.length - 1)}px)"
			src="layerdForestSmall{layer}.png"
			alt="parallax layer {layer}"
		>
	{/each}
</div>

{/if}

<div class="text">
	<span style="opacity: {1 - Math.max(0, y / 40)}">
		scroll down
	</span>

	<div class="foreground">
		You have scrolled {y} pixels

		<div id="box">
			<div class="in">
				<p>Some text0</p>
			</div>
			<div class="in">
				<p>Some text0</p>
			</div>		
		</div>

	</div>
</div>

<style>
	#box{
		display:flex;
		width:100%;
		flex-direction: row;
	}
	.in{
		background-color:white;
		margin: 20px;
		height: 80px;
	}

	.parallax-container {
		position: fixed;
		display: flex;
		align-content: center;
		flex-direction: column;
		width: 100%;
		height: 100%;
		left: 50%;
		transform: translate(-50%,0);
		overflow: hidden;
	}

	.parallax-container img {
		position: absolute;
		width:100%;
		min-height: 800px;
		top: 0;
		left: 0;
		right: 0;
		will-change: transform;
	}

	.parallax-container img:last-child::after {
		content: '';
		position: absolute;
		width: 100%;
		height: 50%;
		background: rgb(45,10,13);
	}
	.parallax-container-small {
		position: fixed;
		display: flex;
		align-content: center;
		flex-direction: column;
		width: 100%;
		height: 100%;
		left: 50%;
		transform: translate(-50%,0);
		overflow: hidden;
	}

	.parallax-container-small img {
		position: absolute;
		width:100%;
		min-height: 800px;
		top: 0;
		left: 0;
		right: 0;
		will-change: transform;
	}

	.parallax-container-small img:last-child::after {
		content: '';
		position: absolute;
		width: 100%;
		height: 50%;
		background: rgb(45,10,13);
	}

	.text {
		position: relative;
		width: 100%;
		height: 300vh;
		color: rgb(220,113,43);
		text-align: center;
		padding: 4em 0.5em 0.5em 0.5em;
		box-sizing: border-box;
		pointer-events: none;
	}

	span {
		display: block;
		font-size: 1em;
		text-transform: uppercase;
		will-change: transform, opacity;
	}

	.foreground {
		position: absolute;
		top: 800px;
		left: 0;
		width: 100%;
		height: calc(100% - 300px);
		background-color: rgb(32,0,1);
		color: white;
		padding: 50vh 0 0 0;
	}

	:global(body) {
		margin: 0;
		padding: 0;
		background-color: rgb(253, 174, 51);
	}
</style>