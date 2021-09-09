<script>
	import Project from './Project.svelte';
</script>

<section id="work">
	<div class="work-container">
		<Project
			orientation={'right'}
			img={'images/ard.jpg'}
			tech={['Node.js', 'Express.js']}
			title={'Archer Rose Digital'}
			description={'This is the website for my freelancing company, Archer Rose Digital. It allows users to view my work and services, as well as contact me through a detailed form.'}
			link={'https://www.archerrosedigital.com/'}
		/>
		<Project
			orientation={'left'}
			img={'images/writeon.jpg'}
			tech={['Node.js', 'Express', 'React', 'MongoDB', 'GraphQL']}
			title={'Write On'}
			description={'This personal project pulls data from the Writing Prompts subreddit to help aspiring writers create better stories. The frontend is built with React, and the backend is an Express GraphQL API.'}
			link={'https://writeon.archerrosedigital.com/'}
			github={'https://github.com/TimothyAllgood/writr_frontend'}
		/>
		<Project
			orientation={'right'}
			img={'images/express-market.jpg'}
			tech={['Node.js', 'Express.js', 'MongoDB']}
			title={'Express Market'}
			description={'This simple ecommerce CMS, allows users to signup and "shop" from a database. It was built as a solo project as part of the curriculum at General Assembly using the MEN stack.'}
			link={'https://obscure-harbor-50614.herokuapp.com/products'}
			github={'https://github.com/TimothyAllgood/express-ecommerce'}
		/>
		<Project
			orientation={'left'}
			img={'images/tamagotchi.jpg'}
			tech={['JavaScript']}
			title={'Project Tamagotchi'}
			description={"This simple tamagotchi clone was built with plain ol' JavaScript. It keeps track of how many times you have lost, fetches data from a weather API to change the background, and changes the user's avatar based on how long it has beem kept alive. "}
			link={'https://pages.git.generalassemb.ly/TimothyAllgood/project-tamagotchi/'}
			github={'https://git.generalassemb.ly/TimothyAllgood/project-tamagotchi'}
		/>
		<Project
			orientation={'right'}
			img={'images/ocd.jpg'}
			tech={['Node.js', 'Express', 'React']}
			title={'O.C.D Cleaning Services'}
			description={'This SPA was built with React to showcase the services of O.C.D Cleaning Services. It allows user to navigate a simple, minimalist interface to learn about the company.'}
			link={'https://ocdcleaningservicesllc.com/#/'}
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
</style>
