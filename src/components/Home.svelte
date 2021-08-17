<script>
	import Splash from './Splash.svelte';
	import About from './About.svelte';
	import Header from './Header.svelte';
	import Work from './Work.svelte';
	import Contact from './Contact.svelte';
	import Social from './Social.svelte';

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
<main>
	<Header />
	<Splash />
	<About />
	<Work />
	<Contact />
	{#if !mobile}
		<Social />
	{/if}
</main>

<style>
	main {
		width: 60vw;
		margin: 0 auto;
	}

	@media (max-width: 1500px) {
		main {
			width: 70vw;
		}
	}

	@media (max-width: 1250px) {
		main {
			width: 80vw;
		}
	}

	@media (max-width: 1150px) {
		main {
			width: 90vw;
		}
	}

	@media (max-width: 1200px) and (min-width: 700px) {
		main {
			width: 70vw;
		}
	}
</style>
