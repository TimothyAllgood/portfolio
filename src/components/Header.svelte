<script>
	let y;
	let open = false;
	const handleScroll = async () => {
		const header = document.querySelector('header');
		if (y > 15) {
			header.classList.add('scrolled');
		} else {
			header.classList.remove('scrolled');
		}
	};
</script>

<svelte:window on:scroll={handleScroll} bind:scrollY={y} />
<header class="desktop">
	<nav>
		<div class="logo"><a href="#home"><img src="images/T.svg" /></a></div>
		<ul>
			<li><a href="#about">About Me</a></li>
			<li><a href="#work">My Work</a></li>
			<li><a href="#contact">Get In Touch</a></li>
			<li><a href="/resume/resume.pdf" target="_blank">Resume</a></li>
		</ul>
	</nav>
</header>

<header class="mobile">
	<nav>
		<div class="logo"><a href="#home"><img src="images/T.svg" /></a></div>
		<div
			class={open ? 'toggle-container open' : 'toggle-container'}
			on:click={() => (open = !open)}
		>
			<span class="toggle" />
		</div>
	</nav>
	<ul class={open ? 'show' : ''}>
		<li><a href="#about">About Me</a></li>
		<li><a href="#work">My Work</a></li>
		<li><a href="#contact">Get In Touch</a></li>
		<li><a href="/resume/resume.pdf" target="_blank">Resume</a></li>
	</ul>
</header>

<style>
	.logo img {
		height: 85px;
		transition: all ease 0.2s;
	}

	.logo img:hover {
		filter: brightness(0.2) sepia(1) hue-rotate(180deg) saturate(5);
	}

	.desktop {
		position: fixed;
		width: 100vw;
		left: 0;
		transition: all ease 0.5s;
		background-color: rgba(92, 219, 149, 0.85);
		backdrop-filter: blur(5px);
		z-index: 111;
	}

	.desktop nav {
		width: 90vw;
		margin: 0 auto;
		display: flex;
		height: 85px;
		justify-content: space-between;
		align-items: center;
		transition: all ease 0.5s;
	}

	.desktop nav ul {
		list-style-type: none;
		display: flex;
	}

	.desktop nav ul li {
		padding: 10px 15px;
		transition: all ease 0.4s;
	}

	.desktop nav ul li:hover {
		background-color: #05386b;

		border-radius: 5px;
	}

	.desktop nav ul li a {
		transition: all ease 0.4s;
	}

	.desktop nav ul li:hover a {
		color: #5cdb95;
	}

	.mobile {
		display: none;
	}

	@media screen and (max-width: 700px) {
		.desktop {
			display: none;
		}

		.mobile {
			display: initial;
			position: fixed;
			width: 100vw;
			left: 0;
			transition: all ease 0.5s;
			background-color: rgba(92, 219, 149, 0.85);
			backdrop-filter: blur(5px);
			z-index: 111;
		}

		.mobile nav {
			width: 90vw;

			margin: 0 auto;
			display: flex;
			height: 85px;
			justify-content: space-between;
			align-items: center;
			transition: all ease 0.5s;
		}

		.mobile ul {
			top: 0;
			position: absolute;
			right: -4000px;
			height: 100vh;
			width: 50vw;
			list-style-type: none;
			transition: all ease 0.5s;
			background-color: #05386b;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
		.mobile ul li {
			width: 100%;
			text-align: center;
			padding: 10px 0;
		}
		.mobile ul li a {
			color: #5cdb95;
			width: 100%;
			padding: 10px 0;
			display: inline-block;
		}

		.mobile .show {
			right: 0;
			z-index: 1;
		}

		.toggle-container {
			width: 35px;
			height: 35px;
			position: relative;
			transition: all ease 0.2s;
		}

		.toggle,
		.toggle::before,
		.toggle::after {
			position: absolute;
			width: 30px;
			height: 4px;
			background-color: #05386b;
			transition: all ease 0.2s;
		}

		.toggle::before {
			content: '';
			top: -10px;
			left: 0;
		}

		.toggle {
			top: 15px;
			left: 2.5px;
		}

		.toggle::after {
			content: '';
			top: 10px;
			left: 0;
		}

		.toggle-container:hover {
			cursor: pointer;
		}

		.toggle-container:hover > .toggle,
		.toggle-container:hover > .toggle::after,
		.toggle-container:hover > .toggle::before {
			background-color: green;
		}

		.open:hover > .toggle {
			background-color: transparent;
		}

		.open {
			margin-right: 47vw;
		}

		.open .toggle {
			background-color: transparent;
		}

		.open .toggle::before {
			top: 0;
			transform: rotate(45deg);
		}

		.open .toggle::after {
			top: 0;
			transform: rotate(-45deg);
		}
	}
</style>
