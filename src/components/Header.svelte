<script>
	let y;
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
<header>
	<nav>
		<div class="logo"><a href="#home">TA</a></div>
		<ul>
			<li><a href="#about">About Me</a></li>
			<li><a href="#work">My Work</a></li>
			<li><a href="#contact">Get In Touch</a></li>
			<li><a href="#contact">Resume</a></li>
		</ul>
	</nav>
</header>

<style>
	header {
		position: fixed;
		width: 100vw;
		left: 0;
		transition: all ease 0.5s;
		background-color: rgba(92, 219, 149, 0.85);
		backdrop-filter: blur(5px);
		z-index: 111;
	}

	nav {
		width: 90vw;
		margin: 0 auto;
		display: flex;
		height: 85px;
		justify-content: space-between;
		align-items: center;
		transition: all ease 0.5s;
	}

	nav ul {
		list-style-type: none;
		display: flex;
	}

	nav ul li {
		padding: 10px 15px;
	}
</style>
