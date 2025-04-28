<script>
	import Hero from "$components/helpers/Hero.svelte";
	import Footer from "$components/Footer.svelte";
	import Scrolly from "$components/helpers/Scrolly.svelte";
	import {fade} from 'svelte/transition';

	/*
		Scrolly is a component that allows you to create a scrollytelling effect.
		- value: Takes on the value of the current scroll step that's most in view.

		When using Scrolly, create a container with the class "sticky" and the CSS in the example below.
		That will create a sticky container that will stay in place while the steps scroll over it.
	*/

	let value = $state();
	let scrollY = $state();
	// svelte-ignore non_reactive_update
	let selected = $state('');

	const explanation = [
		"Oakland was once a thriving sports town, home to three major professional sports teams.",
		"But then the Raiders left.",
		"Followed by the Warriors.",
		"And just last season, the A's played their final game at the Coliseum.",
		"Leaving Oakland a teamless graveyard.",
		"So how did the city get here and what is to come of professional sports in Oakland?"
	];

	$inspect({value,scrollY})


</script>

<!-- svelte-ignore css_unused_selector -->
<svelte:window bind:scrollY={scrollY} />
<section id="scrolly">
	<div class="sticky">
		
		<!-- svelte-ignore a11y_missing_attribute -->
		<img class="hero" class:black-and-white={value>=4} src="demo/assets/images/fieldshot.svg"/>

		{#if value === undefined && scrollY < 2000}
			<div class="headline" transition:fade>
				<h1>OAKTOWN</h1>
				<h2>Dek</h2>
				<h3>Byline</h3>
			</div>
		{/if}

		{#if value === 1 || value === 2 || value === 3}
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFC-Raiders1215.png" style:top={"360px"} 
				style:left={"41px"} style:transform={"rotate(-9deg)"} class:blur={value>=2} 
				class:shadow={value===1} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFC-Raiders1218.png" style:top={"80px"} 
				style:left={"1210px"} class:blur={value>=2}  class:shadow={value===1} transition:fade>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/NYT-Raiders.png" style:top={"539px"} 
				style:left={"946px"} style:transform={"rotate(-7deg)"} class:blur={value>=2}  
				class:shadow={value===1} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SI-Raiders327.jpg" style:top={"44px"} 
				style:left={"112px"} style:transform={"rotate(-5deg)"} class:blur={value>=2} 
				class:shadow={value===1}  transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SI-Raiders1216.jpg" style:top={"715px"} 
				style:left={"715px"} style:transform={"rotate(1deg)"} class:blur={value>=2}  
				class:shadow={value===1} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/ESPN-Raiders.jpg" style:top={"235px"} 
				style:left={"942px"} style:transform={"rotate(5deg)"} class:blur={value>=2} 
				class:shadow={value===1} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/Forbes-Raiders.jpg" style:top={"375px"} 
				style:left={"742px"} style:transform={"rotate(-1deg)"} class:blur={value>=2}  
				class:shadow={value===1} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/MN-Raiders.png" style:top={"175px"} 
				style:left={"372px"} style:transform={"rotate(2deg)"} class:blur={value>=2}  
				class:shadow={value===1} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFC-Raiders1211.png" style:top={"687px"} 
				style:left={"2px"} style:transform={"rotate(4deg)"} style:height={"150px"} class:blur={value>=2} 
				class:shadow={value===1} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/KQED-Raiders.jpg" style:top={"557px"} 
				style:left={"215px"} style:transform={"rotate(0.5deg)"} style:height={"145px"} class:blur={value>=2} 
				class:shadow={value===1} transition:fade/>
		{/if}

		{#if value === 2 || value === 3}
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/ABC-Warriors.png" style:top={"310px"} 
				style:left={"230px"}  class:blur={value>=3} class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/ESPN-Warriors.jpg" style:top={"80px"} 
				style:left={"770px"} style:height={"120"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/Guardian-Warriors.png" style:top={"500px"} 
				style:left={"446px"} style:transform={"rotate(-7deg)"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/LAT-Warriors.png" style:top={"144px"} 
				style:left={"900px"} style:transform={"rotate(-2deg)"} style:height={"100px"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/NBC-Warriors.png" style:top={"715px"} 
				style:left={"985px"} style:transform={"rotate(1deg)"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/NYT-Warriors.png" style:top={"255px"} 
				style:left={"542px"} style:transform={"rotate(-1deg)"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SantaClara-Warriors.png" style:top={"5px"} 
				style:left={"0px"} style:transform={"rotate(-2deg)"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFC-Warriors412.png" style:top={"687px"} 
				style:left={"2px"} style:transform={"rotate(4deg)"} style:height={"150px"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFC-Warriors1014.png" style:top={"570px"} 
				style:left={"855px"} style:transform={"rotate(2deg)"} style:height={"145px"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFGATE-2013.png" style:top={"400px"} 
				style:left={"1000px"} style:transform={"rotate(0deg)"} style:height={"145px"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFGATE-Warriors.png" style:top={"500px"} 
				style:left={"0px"} style:transform={"rotate(-4deg)"} style:height={"145px"} class:blur={value>=3} 
				class:shadow={value===2} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/NYT-Warriors2015.png" style:top={"700px"} 
				style:left={"542px"} style:transform={"rotate(-1deg)"} class:blur={value>=3} class:shadow={value===2} 
				transition:fade/>
		{/if}

		{#if value === 3}
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/Atlantic-Athletics.png" style:top={"80px"} 
				style:left={"800px"} style:height={"120"} class:shadow={value===3} transition:fade>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/CBS-Athletics.jpg" style:top={"290px"} 
				style:left={"6px"} style:transform={"rotate(-7deg)"} style:height={"200px"}
				class:shadow={value===3} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/CBS-Athletics.png" style:top={"120px"} 
				style:left={"700px"} style:transform={"rotate(-7deg)"} style:height={"200px"} class:shadow={value===3}
				transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/ESPN-Athletics.jpeg" style:top={"1px"} 
				style:left={"85px"} style:transform={"rotate(1deg)"} class:shadow={value===3} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/Forbes-Athletics.png" style:top={"240px"} 
				style:left={"1042px"} style:transform={"rotate(-1deg)"} class:shadow={value===3} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/LAT-Athletics.png" style:top={"150px"} 
				style:left={"0px"} style:transform={"rotate(-2deg)"} style:height={"130px"} class:shadow={value===3} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/NBC-Athletics.png" style:top={"523px"} 
				style:left={"2px"} style:transform={"rotate(4deg)"} style:height={"150px"} class:shadow={value===3} 
				transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/NYT-Athletics.png" style:top={"420px"} 
				style:left={"1000px"} style:transform={"rotate(0deg)"} style:height={"145px"}
				class:shadow={value===3} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFC-Athletics.png" style:top={"420px"} 
				style:left={"400px"} style:transform={"rotate(0deg)"} style:height={"145px"} 
				class:shadow={value===3} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFC-Athletics2.png" style:top={"700px"} 
				style:left={"523px"} style:transform={"rotate(-1deg)"} class:shadow={value===3}
				transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SFGATE-Athletics.png" style:top={"300px"} 
				style:left={"400px"} style:height={"135px"} style:transform={"rotate(4deg)"} class:shadow={value===3} 
				transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SI-Athletics.jpg" style:top={"670px"} 
				style:left={"2px"} style:transform={"rotate(-1deg)"} style:height={"190px"} class:shadow={value===3}
				transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/SI-Athletics2.jpg" style:top={"10px"} 
				style:left={"1090px"} style:transform={"rotate(2deg)"} class:shadow={value===3} 
				transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/NBC-Athletics2.png" style:top={"570px"} 
				style:left={"725px"} style:transform={"rotate(2deg)"} style:height={"145px"}
				class:shadow={value===3} transition:fade/>
			<!-- svelte-ignore a11y_missing_attribute -->
			<img class="newshead" src="demo/assets/images/headlines/ABC-Athletics.png" style:top={"770px"} 
				style:left={"1330px"} class:shadow={value===3} transition:fade/>
		{/if}

		<!-- {#if value >=4}
			<img class="hero" src="demo/assets/images/fieldshotBW.svg" transition:fade>
		{/if} -->

	</div>

	<div class="spacer"></div>

	<Scrolly bind:value>
		{#each explanation as text, i}
			{@const active = value === i}
			<div class="step" class:active>
				<p>{text}</p>
			</div>
		{/each}
	</Scrolly>

	<div class="spacer" style:height="50vh"></div>

</section>


<section>
	<div class="text">
		<h4>Click each section to explore the impact of professional sports in Oakland.</h4>
	</div>

	<div class="box">
	</div>

	<nav class="navbar">
		<!-- svelte-ignore event_directive_deprecated -->
		<button on:click={() => selected = 'roots'}>The Roots</button>
		<!-- svelte-ignore event_directive_deprecated -->
		<button on:click={() => selected = 'city'}>The City</button>
		<!-- svelte-ignore event_directive_deprecated -->
		<button on:click={() => selected = 'fans'}>The Fans</button>
	</nav>

	<div class="box">
	</div>

	{#if selected}
		<section class="dynamic-content">
			{#if selected === 'roots'}
				<div class="content">
					<h2>Roots Content</h2>
					<p>This is the Roots section.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
					<p>putting in a bunch of paragraphs to see a whole page.</p>
				</div>
			{:else if selected === 'city'}
				<h2>City Content</h2>
				<p>This is where the timeline will go.</p>
			{:else if selected === 'fans'}
				<h2>Fans Section</h2>
				<p>This is the fans section</p>
			{/if}
		</section> 
	{/if}
	  
</section>
	

<style>
	.sticky {
		position: sticky;
		top: 0;
		z-index: -1;
		width: 100vw;
		height: 100vh;
	}

	.hero {
		height: 100%;
		width: 100%;
		object-fit: cover;
		transition: filter 2s;
	}

	.spacer {
		height: 75vh;
	}

	.step {
		margin: 80vh auto;
		background: var(--color-gray-100);
		text-align: center;
		width: 40vw;
		box-shadow: 5px 5px 10px 2px rgb(0 0 0 / 0.8);
		font-size: x-large;
	}

	.step:last-of-type {
		margin-bottom: 0;
	}

	.step p {
		padding: 1rem;
	}

	span {
		background: var(--color-mark);
		padding: 0 8px;
	}

	.headline {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		color: white;
		background: rgba(0, 0, 0, 0.5);
		padding: 0 1rem;
		text-align: center;
	}

	.newshead {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		color: white;
		text-align: center;
		height: 160px; 
	}

	img {
		position: absolute;
		height: 100px;
	}
	
	.black-and-white {
		filter: grayscale(100%);
	}

	.blur {
		filter: blur(0.07px) grayscale(100%);
		opacity: 95%;
	}

	.shadow {
		box-shadow: 5px 5px 10px 2px rgb(0 0 0 / 0.8);
	}

	.navbar {
		display: flex;
		gap: 7rem;
		padding: 0.7rem 0;
		justify-content: center;
		margin-top: 2rem;
		margin-bottom: 2rem;
		background: #2e86ab;

		position: sticky;
		top: 0;
		z-index: 10;
		margin: 0;
	}

	.dynamic-content {
		padding: 2rem;
		background: #254441;
		color: white; 
	}

	button {
		padding: 0.5rem 1rem;
		font-size: 2rem;
		border: 2px solid black; 
		border-radius: 8px;
		color: #FCE354;
		background-color: #15BA7D;
		box-shadow: 6px 6px #254441;
	}

	.text {
		text-align: center;
		margin-top: 2rem;
		margin-bottom: 2rem;
	}
	
	.content {
		text-align: center;
	}

	.box {
		background-color: #2e86ab;
		padding: 1.5rem;
		margin: 0;
	}

</style>


<Footer />
