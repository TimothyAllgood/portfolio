<script>
	import Project from './Project.svelte';
</script>

<section id="work">
	<div class="work-container">
		<Project
			orientation={'right'}
			img={'https://source.unsplash.com/random/1920x1080'}
			tech={['Node.js', 'Express.js', 'React', 'MongoDB']}
			title={'DnDGo'}
			description={'DnDGo is a full stack web app, that aims to connect people interested in tabletop role playing games, such as Dungeons and Dragons. '}
		/>
		<Project
			orientation={'left'}
			img={'https://source.unsplash.com/random/1920x1080'}
			tech={['Node.js', 'Express.js', 'MongoDB']}
			title={'Express Market'}
			description={'This simple ecommerce CMS, allows users to signup and "shop" from a database'}
		/>
		<Project
			orientation={'right'}
			img={'https://source.unsplash.com/random/1920x1080'}
			tech={['Python', 'Django', 'PostgreSQL']}
			title={'Project Wayfarer'}
			description={'This app was designed as part of the curriculum at General Assembly. It was a group project, assigned by the instructional team. We were given a week to design and develop a platform that basically acts as a travel blog, with user authentication, and the ability for users to add posts on each location'}
		/>
	</div>
</section>

<style>
	section {
		width: 100%;
		min-height: 100vh;
		/* max-height: 100vh; */
		text-align: center;
		display: grid;
		place-items: center;
		scroll-margin-top: 100px;
	}
	h1 {
		color: #05386b;
		text-transform: uppercase;
		font-size: 4em;
	}
</style>
