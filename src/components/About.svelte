<script>
	import { onMount } from 'svelte';
	import { fly, fade } from 'svelte/transition';
	let visible = false;
	onMount(() => {
		let aboutObserver = new IntersectionObserver(
			(entries, observer) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						visible = true;
						aboutObserver.unobserve(entry.target);
					} else {
						visible = false;
					}
				});
			},
			{ rootMargin: '0px 0px -200px 0px' }
		);
		aboutObserver.observe(document.querySelector('#about'));
	});
</script>

<section id="about">
	<div class="about-container">
		{#if visible}
			<h4 transition:fly={{ y: 200, duration: 1000 }}>About Me</h4>
			<div class="inner-about">
				<div class="left" transition:fly={{ y: 200, duration: 1000 }}>
					<p>
						And when we woke up, we had these bodies. Anyhoo, your net-suits
						will allow you to experience Fry's worm infested bowels as if you
						were actually wriggling through them. Morbo will now introduce
						tonight's candidates…
					</p>
					<p>
						PUNY HUMAN NUMBER ONE, PUNY HUMAN NUMBER TWO, and Morbo's good
						friend, Richard Nixon. And until then, I can never die? Shut up and
						get to the point! You know the worst thing about being a slave? They
						make you work, but they don't pay you or let you go. Maybe I love
						you so much I love you no matter who you are pretending to be.
					</p>
					<p>Here is a list of some the technologies I've been using:</p>
					<div class="tech">
						<ul>
							<li>JavaScript</li>
							<li>React</li>
							<li>Node.js</li>
						</ul>
						<ul>
							<li>GraphQL</li>
							<li>GraphQL</li>
							<li>GraphQL</li>
						</ul>
					</div>
				</div>
				<div class="right" transition:fly={{ y: 200, duration: 1000 }}>
					<img src="https://source.unsplash.com/random/1920x1080" alt="" />
				</div>
			</div>
		{/if}
	</div>
</section>

<style>
	#about {
		width: 100%;
		height: 100vh;
		/* text-align: center; */
		display: grid;
		place-items: center;
	}

	.about-container {
		scroll-snap-align: start;
	}

	.inner-about {
		display: flex;
	}

	.inner-about p,
	.about-container h4 {
		padding-bottom: 25px;
	}

	.tech {
		margin-left: 25px;
		display: flex;
	}

	.tech ul {
		margin-right: 50px;
	}

	.right {
		margin-left: 50px;
	}

	img {
		width: 100%;
		min-width: 100%;
		height: 100%;
		object-fit: cover;
		position: relative;
		border-radius: 5px;
	}

	.right {
		position: relative;
		transition: all ease 0.3s;
		border-radius: 5px;
	}

	.right:hover {
		transform: scale(0.97);
		box-shadow: 10px 10px 5px rgb(5, 56, 107, 0.4);
	}

	.right::after {
		content: '';
		width: 100%;
		height: 100%;
		position: absolute;
		top: 0;
		left: 0;
		background-color: #05386b;
		opacity: 0.5;
		border-radius: 5px;
		transition: all ease 0.3s;
	}

	.right:hover::after {
		opacity: 0;
	}

	@media screen and (max-width: 700px) {
		#about {
			scroll-margin-top: 100px;
			height: 100%;
			margin-bottom: 50px;
		}
	}
</style>
