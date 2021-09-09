<script>
	import { onMount } from 'svelte';
	import { fly } from 'svelte/transition';
	import { cubicInOut } from 'svelte/easing';
	export let orientation;
	export let img;
	export let tech;
	export let title;
	export let description;
	export let link;
	export let github;
	let component;
	let visible = false;
	onMount(() => {
		let observer = new IntersectionObserver(
			(entries, observer) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						visible = true;
						observer.unobserve(entry.target);
					} else {
						visible = false;
					}
				});
			},
			{ rootMargin: '0px 0px -200px 0px' }
		);
		observer.observe(component);
		// component.
		// document.querySelectorAll('.project').forEach((project) => {
		// 	observer.observe(project);
		// });
	});
</script>

<section class={`project ${orientation}`} bind:this={component}>
	{#if visible}
		<div
			class="image"
			transition:fly={{ y: 200, duration: 1000, easing: cubicInOut }}
			on:click={() => window.open(link, '_blank').focus()}
		>
			<img src={img} alt="" />
		</div>

		<div
			class="info"
			transition:fly={{ y: 100, duration: 1000, easing: cubicInOut }}
		>
			<div class="title">
				<h3><a href={link} target="_blank">{title}</a></h3>
			</div>
			<div class="description">
				<p>
					{description}
				</p>
			</div>
			<div class="bottom">
				<div class="tech">
					{#each tech as item}
						<p>{item}</p>
					{/each}
				</div>
				<div class="links">
					{#if github}
						<a href={github} target="_blank"><i class="fab fa-github" /></a>
					{/if}
					<a href={link} target="_blank"
						><i class="fas fa-external-link-alt" /></a
					>
				</div>
			</div>
		</div>
	{/if}
</section>

<style>
	.project {
		display: flex;
		margin-bottom: 50px;
		position: relative;
		height: 100%;
	}

	.project .image {
		width: 60%;
		/* width: 100%; */
		position: relative;
		transition: all ease 0.2s;
	}

	.project .image:hover {
		cursor: pointer;
		transform: scale(1.01);
	}

	.project .image::after {
		content: '';
		width: 100%;
		height: 100%;
		position: absolute;
		top: 0;
		left: 0;
		background-color: #05386b;
		opacity: 0.3;
		border-radius: 5px;
		transition: all ease 0.5s;
	}

	.project .image:hover::after {
		background-color: transparent;
	}

	.project .image img {
		width: 100%;
		min-width: 100%;
		height: 100%;
		border-radius: 5px;
		object-fit: cover;
	}

	.project .info {
		width: 70%;
		display: grid;
		grid-template-rows: 10% 70% 20%;
		z-index: 1;
		margin: 2.5% 0;
		align-items: center;
	}

	.project .info .description {
		padding: 1em;
		border-radius: 5px;
		color: #05386b;
		background-color: #47ce84;
		display: flex;
		justify-content: center;
		align-items: center;
		margin: 2.5% 0;
		min-height: 100px;
	}

	.title {
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
	}

	.bottom {
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
	}

	.links,
	.tech {
		display: flex;
		justify-content: flex-end;
	}

	.tech {
		margin-bottom: 10px;
	}

	.tech p:not(:first-of-type) {
		margin-left: 10px;
	}

	.links a {
		font-size: 1.2rem;
	}

	.links a:first-of-type {
		padding-right: 20px;
	}

	.right {
		text-align: right;
	}

	.right .image {
		margin-right: 25px;
	}

	.right .info {
		margin-left: -150px;
	}

	.left {
		flex-direction: row-reverse;
		text-align: left;
	}

	.left .info .description {
		justify-content: initial;
	}

	.left .info {
		margin-right: -150px;
	}

	.left .image {
		margin-left: 25px;
	}

	.left .links,
	.left .tech {
		justify-content: flex-start;
	}

	@media screen and (max-width: 700px) {
		.project {
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}

		.left .info,
		.right .info {
			margin-left: 0;
			margin-right: 0;
		}

		.title {
			text-align: center;
		}

		.left .image,
		.right .image {
			width: 70%;
			margin: 0;
		}
	}
</style>
