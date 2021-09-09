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
	<a href="https://github.com/TimothyAllgood/portfolio" target="_blank">
		Designed and Built by Timothy Allgood using Svelte.
	</a>
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
