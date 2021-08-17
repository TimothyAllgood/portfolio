<script>
	import { onMount } from 'svelte';
	let mobile = false;

	const checkMedia = () => {
		let mql = window.matchMedia('(max-width: 700px)');
		if (mql.matches) {
			mobile = true;
		} else {
			mobile = false;
		}
	};
	onMount(() => {
		checkMedia();
	});
</script>

<svelte:window on:resize={checkMedia} />

<footer>
	{#if mobile}<p>Mobile</p>{/if}
	<a href="#">Designed and Built by Timothy Allgood</a>
</footer>

<style>
	footer {
		place-self: end center;
		padding: 25px 0;
		z-index: 10;
	}
	footer a {
		transition: all ease 0.3s;
	}

	footer a:hover {
		color: #031d38;
	}
</style>
