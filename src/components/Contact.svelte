<script>
	import Footer from './Footer.svelte';
</script>

<section id="contact">
	<div class="inner">
		<h1>Get In Touch</h1>
		<p>
			I'm currently on the market for a new role with , and my inbox is always
			open. Whether you have a role you're filling, a question or just want to say hi, contact me and lets talk!
		</p>
		<div class="buttons">
			<div class="btn">
				<a href="mailto:timothyallgood@gmail.com">timothyallgood@gmail.com</a>
			</div>
			<div class="btn"><a href="tel:985-773-9525">985.773.9525</a></div>
		</div>
	</div>
	<Footer />
</section>

<style>
	section {
		width: 100%;
		height: 50vh;
		text-align: center;
		display: grid;
		place-items: center center;
		position: relative;
	}

	.inner {
		width: 50%;
	}

	p {
		margin-top: 25px;
	}

	.buttons {
		display: flex;
		justify-content: center;
		margin-top: 25px;
	}

	.btn a {
		border: 1px solid #05386b;
		padding: 10px 15px;
		border-radius: 5px;
		margin: 0 10px;
		transition: all ease 0.2s;
	}

	.btn a:hover {
		background-color: #05386b;
		color: #5cdb95;
	}

	@media screen and (max-width: 700px) {
		section {
			height: 80vh;
			place-items: start center;
		}
	}
</style>
