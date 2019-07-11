<script>
	import { UIButton, UIInput, Ripple, IconButton, Switch } from 'svelte-toolbox';

	let value = "";
	let darkMode = false;
</script>

<style>
	div {
		overflow: auto;
	}
	.left {
		float: left;
	}
	.right {
		float: right;
		height: 48px;
	}
	.switch-text-container {
		line-height: 48px;
	}
	.disabled {
		opacity: 0.4;
	}
	.rounded {
		border-radius: 3px;
	}

	.switch-container {
		max-width: 800px;
		margin: auto;
		padding: 5px 20px;
		background-color: rgba(0, 0, 0, 0.1);
		border-bottom: 0.1px solid rgba(0, 0, 0, 0.2)
	}
</style>

<svelte:head>
    <title>Home</title>
</svelte:head>

{#if darkMode}
	<style>
		body {
			background-color: rgba(0, 0, 0, 0.7);
			color: white;
		}
	</style>
{/if}

<UIButton block={true}>Button</UIButton>

<UIInput block={true} placeholder="Type something here" bind:value/>
{value}
<UIInput block={true} placeholder="Input Outlined" outlined={true}/>

<Ripple>
	<p>
		There is a ripple effect here
	</p>
</Ripple>

<div>
	<IconButton icon="error"/>
</div>

<div class="rounded">
	<div class="switch-container">
		<span class="left switch-text-container">Dark Mode</span>
		<span class="right">
			<Switch bind:on={darkMode}/>
		</span>
	</div>
	<div class="switch-container">
		<span class="left switch-text-container disabled">Disabled Option</span>
		<span class="right">
			<Switch disabled={true}/>
		</span>
	</div>
</div>
