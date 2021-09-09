<script>
</script>

<section id="home">
	<div class="splash-text">
		<h3 class="greeting">Hello my name is,</h3>
		<h1>Timothy Allgood</h1>
		<h2>I design and develop cool sh*t.</h2>
		<h3>
			I'm a software engineer, specializing in MERN stack web apps. I'm on the
			hunt for a badass company, looking for a highly skilled team player to add
			to their roster.
		</h3>
		<!-- <img src="./images/pc.png" alt="" /> -->
	</div>
</section>

<style>
	section {
		width: 100%;

		min-height: 100vh;
		text-align: center;
		display: grid;
		place-items: center;
	}

	.splash-text {
		text-align: left;
	}

	.greeting {
		font-weight: 400;
		font-size: 1.5em;
	}
	h3 {
		width: 50%;
		font-weight: 400;
		font-size: 1.2em;
	}

	h1 {
		color: #05386b;
		text-transform: uppercase;
		font-size: 5em;
	}

	h2 {
		color: rgb(1, 45, 88);
		font-size: 2.1em;
		margin-bottom: 25px;
		font-style: italic;
	}

	@media screen and (max-width: 1070px) {
		section {
			max-height: initial;
			height: 100%;
			padding: 100px 0 50px;
		}
	}
</style>
