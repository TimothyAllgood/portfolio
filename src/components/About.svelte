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
			<h4 transition:fly={{ y: 200, duration: 1000 }}>
				Where I Talk About Myself
			</h4>
			<div class="inner-about">
				<div class="left" transition:fly={{ y: 200, duration: 1000 }}>
					<p>
						It was cold and rainy fall evening many moons ago when I stumbled
						upon the encumbersome mess that is JavaScript. Thus my software
						engineering journey was born. <br /><br />
						Ok . . . I really don't remember the time of year it was but I was a
						senior in high school when I started programing, 12+ years ago. Over
						the years I have learned many other languages, had the honor of developing
						numerous websites for some truly inspiring non-profits and startups,
						and really grown to feel immense pride in being a software engineer,
						dedicated to the ever evolving world of technology.
					</p>
					<p>
						The man who helped raise me and shape me into the man I am today
						passed away this August. He taught me how to work hard, love my
						family well and always help anyone you can. Since his passing, I've
						stepped up to help financially take care of the family he has left
						behind along with my own family. This is my WHY for my job hunt,
						this is my REASON for showing up and giving my all, this is why I
						will be the best asset to any company that will give me that
						oppurtunity.
					</p>
					<h5>Here is a list of some of the languages my fingers speak:</h5>
					<div class="tech">
						<ul>
							<li><i class="fab fa-js" /> JavaScript</li>
							<li><i class="fab fa-react" /> React</li>
							<li><i class="fab fa-node-js" /> Node.js</li>
						</ul>
						<ul>
							<li><i class="fab fa-python" /> Python</li>
							<li><i class="icon mongo" /> MongoDB</li>
							<li><i class="icon graphql" /> GraphQL</li>
						</ul>
					</div>
					<div class="music">
						<a href="">
							<h5>Here's what I'm listening to</h5>
						</a>
						<iframe
							src="https://open.spotify.com/embed/playlist/5LJCB7UfWkA4FyTk5hbzwl?theme=0"
							width="100%"
							height="80"
							frameBorder="0"
							allowtransparency="true"
							allow="encrypted-media"
						/>
					</div>
				</div>
				<div class="right" transition:fly={{ y: 200, duration: 1000 }}>
					<img src="images/timothy.jpg" alt="" />
				</div>
			</div>
		{/if}
	</div>
</section>

<style>
	#about {
		width: 100%;
		min-height: 100vh;
		padding-bottom: 50px;
		/* text-align: center; */
		display: grid;
		place-items: center;
	}

	h4 {
		font-size: 1.5em;
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
		margin-top: 25px;
		display: flex;
	}

	.tech ul {
		margin-right: 50px;
		list-style-type: none;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: flex-start;
	}

	.tech ul li {
		padding-bottom: 10px;
	}

	.music {
		margin: 0;
		margin-top: 10px;

		font-size: 1.2em;
	}

	.music a {
		display: inline-block;
		margin-bottom: 10px;
	}

	.right {
		margin-left: 50px;
	}

	img {
		width: 30vw;
		min-width: 100%;
		height: 100%;
		object-fit: cover;
		position: relative;
		border-radius: 5px;
	}

	.mongo {
		background: url('../images/mongodb.svg');
	}

	.graphql {
		background: url('../images/graphql.svg');
	}

	.fab {
		font-size: 1.2em;
	}

	.icon {
		display: inline-block;
		text-indent: -9999px;
		width: 1.2em;
		height: 1.2em;
		background-size: contain;
		background-repeat: no-repeat;
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

	@media screen and (max-width: 1200px) {
	}

	@media screen and (max-width: 700px) {
		#about {
			scroll-margin-top: 100px;
			height: 100%;
			margin-bottom: 50px;
		}

		.inner-about {
			flex-direction: column-reverse;
		}
		.right {
			margin-left: 0;
			margin-bottom: 50px;
		}
		.right img {
			width: 100%;
			height: 300px;
			object-position: top;
			object-fit: cover;
			position: relative;
			border-radius: 5px;
			margin-left: 0rem;
		}

		.tech {
			margin-left: 0px;
			justify-content: space-evenly;
		}

		.tech ul {
			margin-right: 0px;
		}
	}
</style>
