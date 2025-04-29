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
	let selected = $state('roots');

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
					<h1 class="title" style:font-size={"10rem"} style:line-height={"1"} style:margin={"2rem"}>OAKTOWN</h1>
					<h6 style:margin-bottom={"3rem"} style:text-wrap-style="balance">A city once spoiled with championship 
						teams is learning to rebuild its sports scene from the 'roots' up.</h6>
					<p style:margin-bottom={"2.2rem"} style:font-weight="50">By Marquis Chambers, Riley Ramirez, Jessica Blough and Daniella Sandoval</p>
				</div>
				
			{/if}

		<div class="news-container">
			{#if value === 1 || value === 2 || value === 3}
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Raiders1215.png" style:top={"43%"} 
					style:left={"3%"} style:transform={"rotate(-9deg)"} class:blur={value>=2} 
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Raiders1218.png" style:top={"0%"} 
					style:right={"0%"} class:blur={value>=2}  class:shadow={value===1} transition:fade>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NYT-Raiders.png" style:top={"61%"} 
					style:right={"3%"} style:transform={"rotate(-7deg)"} class:blur={value>=2}  
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SI-Raiders327.jpg" style:top={"4%"} 
					style:left={"2%"} style:transform={"rotate(-5deg)"} class:blur={value>=2} 
					class:shadow={value===1}  transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SI-Raiders1216.jpg" style:top={"81%"} 
					style:right={"35%"} style:transform={"rotate(1deg)"} class:blur={value>=2}  
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/ESPN-Raiders.jpg" style:top={"27%"} 
					style:left={"63%"} style:transform={"rotate(5deg)"} class:blur={value>=2} 
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/Forbes-Raiders.jpg" style:top={"45%"} 
					style:left={"50%"} style:transform={"rotate(-1deg)"} class:blur={value>=2}  
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/MN-Raiders.png" style:top={"20%"} 
					style:left={"27%"} style:transform={"rotate(2deg)"} class:blur={value>=2}  
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Raiders1211.png" style:top={"81%"} 
					style:left={"0.5%"} style:transform={"rotate(4deg)"} style:height={"15%"} class:blur={value>=2} 
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/KQED-Raiders.jpg" style:top={"65%"} 
					style:left={"15%"} style:transform={"rotate(0.5deg)"} style:height={"15%"} class:blur={value>=2} 
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFGATE-Raiders.png" style:top={"83%"} 
					style:right={"0%"} style:transform={"rotate(-2deg)"} style:height={"17%"} class:blur={value>=2}  
					class:shadow={value===1} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/yahoo-Raiders.png" style:top={"0%"} 
					style:left={"32%"} style:transform={"rotate(-1deg)"} style:height={"11%"} class:blur={value>=2}  
					class:shadow={value===1} transition:fade/>
			{/if}
		
			{#if value === 2 || value === 3}
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/ABC-Warriors.png" style:top={"24%"} 
					style:left={"0.5%"}  class:blur={value>=3} class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/ESPN-Warriors.jpg" style:top={"7%"} 
					style:right={"30%"} style:height={"15%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/Guardian-Warriors.png" style:top={"46%"} 
					style:right={"35%"} style:transform={"rotate(-7deg)"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/LAT-Warriors.png" style:top={"1%"} 
					style:right={"0.5%"} style:transform={"rotate(-2deg)"} style:height={"11%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NBC-Warriors.png" style:top={"76%"} 
					style:right={"1%"} style:transform={"rotate(1deg)"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NYT-Warriors.png" style:top={"27%"} 
					style:left={"28%"} style:transform={"rotate(-1deg)"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SantaClara-Warriors.png" style:top={"0.5%"} 
					style:left={"0%"} style:transform={"rotate(-2deg)"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Warriors412.png" style:top={"67%"} 
					style:left={"1%"} style:transform={"rotate(3deg)"} style:height={"15%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Warriors1014.png" style:top={"61%"} 
					style:right={"25%"} style:transform={"rotate(2deg)"} style:height={"14%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFGATE-2013.png" style:top={"40%"} 
					style:right={"3%"} style:transform={"rotate(0deg)"} style:height={"14%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFGATE-Warriors.png" style:top={"50%"} 
					style:left={"0%"} style:transform={"rotate(-4deg)"} style:height={"14%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NYT-Warriors2015.png" style:top={"75%"} 
					style:right={"30%"} style:transform={"rotate(0deg)"} class:blur={value>=3} class:shadow={value===2} 
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/USAToday-Warriors.png" style:top={"60%"} 
					style:right={"0%"} style:transform={"rotate(-1deg)"} style:height={"14%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/AP-Warriors.png" style:top={"19%"} 
					style:right={"0%"} style:transform={"rotate(1deg)"} style:height={"13%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/BR-Warriors.png" style:top={"83%"} 
					style:left={"15%"} style:transform={"rotate(-3deg)"} style:height={"15%"} class:blur={value>=3} 
					class:shadow={value===2} transition:fade/>
			{/if}
		
			{#if value === 3}
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/Atlantic-Athletics.png" style:top={"1%"} 
					style:right={"30%"} style:height={"14%"} class:shadow={value===3} transition:fade>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/CBS-Athletics.jpg" style:top={"33%"} 
					style:left={"0%"} style:transform={"rotate(-7deg)"} style:height={"21%"}
					class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/CBS-Athletics.png" style:top={"16%"} 
					style:left={"35%"} style:transform={"rotate(-7deg)"} style:height={"19%"} class:shadow={value===3}
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/ESPN-Athletics.jpeg" style:top={"0%"} 
					style:left={"3%"} style:transform={"rotate(1deg)"} class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/Forbes-Athletics.png" style:top={"24%"} 
					style:right={"18%"} style:transform={"rotate(-1deg)"} class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/LAT-Athletics.png" style:top={"19%"} 
					style:left={"0%"} style:transform={"rotate(-2deg)"} style:height={"13%"} class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NBC-Athletics.png" style:top={"56%"} 
					style:left={"4%"} style:transform={"rotate(4deg)"} style:height={"15%"} class:shadow={value===3} 
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NYT-Athletics.png" style:top={"49%"} 
					style:right={"0%"} style:transform={"rotate(0deg)"} style:height={"14%"}
					class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Athletics.png" style:top={"42%"} 
					style:left={"28%"} style:transform={"rotate(0deg)"} style:height={"14%"} 
					class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Athletics2.png" style:top={"84%"} 
					style:right={"30%"} style:transform={"rotate(1deg)"} class:shadow={value===3}
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFGATE-Athletics.png" style:top={"1%"} 
					style:left={"20%"} style:height={"12%"} style:transform={"rotate(4deg)"} class:shadow={value===3} 
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SI-Athletics.jpg" style:top={"80%"} 
					style:left={"0%"} style:transform={"rotate(-3deg)"} style:height={"19%"} class:shadow={value===3}
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SI-Athletics2.jpg" style:top={"3%"} 
					style:right={"2%"} style:transform={"rotate(2deg)"} class:shadow={value===3} 
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NBC-Athletics2.png" style:top={"59%"} 
					style:right={"28%"} style:transform={"rotate(2deg)"} style:height={"14%"}
					class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/ABC-Athletics.png" style:top={"80%"} 
					style:right={"5%"} class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/NYT-AthleticsLights.png" style:top={"70%"} 
					style:left={"30%"} style:transform={"rotate(0deg)"} 
					class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/SFC-Athletics63.png" style:top={"34%"} 
					style:right={"0%"} style:transform={"rotate(-7deg)"} style:height={"9%"}
					class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/Forbes-Athletics420.png" style:top={"65%"} 
					style:right={"1%"} style:transform={"rotate(3deg)"} style:height={"20%"}
					class:shadow={value===3} transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/AP-Athletics.png" style:top={"40%"} 
					style:right={"25%"} style:transform={"rotate(2deg)"} style:height={"10%"} class:shadow={value===3} 
					transition:fade/>
				<!-- svelte-ignore a11y_missing_attribute -->
				<img class="newshead" src="demo/assets/images/headlines/USAToday-Athletics.png" style:top={"33%"} 
					style:left={"20%"} style:transform={"rotate(4deg)"} style:height={"10%"}
					class:shadow={value===3} transition:fade/>
			{/if}
		</div>
``</div>

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
		<h4><strong>Click</strong> each section to explore the impact of professional sports in Oakland.</h4>
	</div>

	<div class="box">
	</div>

	<nav class="navbar">
		<!-- svelte-ignore event_directive_deprecated -->
		<button on:click={() => selected = 'roots'} class:active={selected === "roots"}>The Roots</button>
		<!-- svelte-ignore event_directive_deprecated -->
		<button on:click={() => selected = 'city'} class:active={selected === "city"}>The City</button>
		<!-- svelte-ignore event_directive_deprecated -->
		<button on:click={() => selected = 'fans'} class:active={selected === "fans"}>The Fans</button>
	</nav>

	<div class="box">
	</div>

	{#if selected}
		<section class="dynamic-content">
			{#if selected === 'roots'}
				
				<div class="content">
					<h2 class="title" style:font-size={"5rem"} style:text-align="center">The Roots</h2>
					<p>The Oakland Coliseum has come alive again with the Oakland Roots announcing 
						at the start of their 2025 season they would be using the Oakland Coliseum 
						as their home field. While it was a short term focus for the roots, they 
						have shifted their focus to the Coliseum becoming their permanent home field. </p>
						
					<p>	A community that was left heartbroken again when the Oakland Athletics whose 
						slogan read “ Rooted in Oakland” uprooted to Sacramento as they prepared to 
						play their 2025 season while they waited for their stadium in Vegas to be finished.  </p>
						
					<p>	What does this mean for the Oakland community?  </p>
						
					<p>	The Roots have revitalized the spirit of the community by bringing a refreshing 
						and much-needed sense of energy back into the local sports scene. Their exciting, 
						gritty style of play resonates deeply with Oakland residents, reflecting the same 
						toughness and resilience that fans have long associated with teams that played at 
						the Coliseum. </p>
						
					<p>	Dave Newhouse, fresh out of college with a journalism degree, landed a job at the 
						Oakland Tribune in 1964. Over a career that spanned nearly five decades before his 
						retirement in 2011, Newhouse developed a deep understanding of the Oakland community. </p>
						
					<p>	“But one thing about Oakland, it's feisty,” Newhouse said. “You know, It may not be 
						recognized, but it's feisty and it battles.” </p>
						
					<p>	Whether it was the hard nosed style of the Raiders, the fearless attitude of the A’s, 
						or the passionate intensity of the Warriors, Oakland sports have always embodied a 
						sense of pride, perseverance, and authenticity. </p>
						
					<p>	The Roots continue that tradition, offering the community a team that mirrors its 
						identity, hardworking, fearless, and proud. Their presence goes beyond just what 
						happens on the field; they have reconnected the city with a sense of belonging and 
						hope, at a time when the loss of other major teams left a void in Oakland’s sporting 
						landscape. </p>
						
					<p>	Camden Riley, defender and midfielder for the Roots who is actively involved with the 
						community knows how important it is for him and the club to be active in the community.  </p>
						
					<p>	“I commonly am in the community going to soccer practices, trying to help out kids 
						and try and just grow a passion for the game,” Riley said. “Whether it be soccer or 
						another sport in Oakland.” </p>
						
					<p>	Riley’s presence along with the Roots at local practices is more than just about 
						teaching a sport; it's about nurturing dreams in a city that has always fought to keep 
						them alive. By inspiring kids to find their passion, they are  helping to build a future 
						where sports are not just an outlet, but a lifeline.</p>
						
					<p>	In Oakland, where grit and heart have always been part of the fabric, it’s leaders like 
						Riley who remind individuals that true change begins in the small moments. </p>
						
					<p>	In many ways, the Roots are not just playing soccer they are carrying on a cultural legacy 
						that has defined Oakland sports for generations. </p>
						
				</div>

			{:else if selected === 'city'}
				<div class="content">
				<h2 class="title" style:font-size={"5rem"} style:text-align="right">The City</h2>
				<p>This is where the timeline will go.</p>
				</div>

			{:else if selected === 'fans'}
				<div class="content">
				<h2 class="title" style:font-size={"5rem"} style:text-align="left">The Fans</h2>
				<!-- (At the start of this section : Let's code in our Fan Interview’s that Jess is working on ) -->
				<p>A new chapter is unfolding for Oakland sports fans across three teams: the Oakland Ballers bringing 
					baseball to Raimondi Park, the Oakland Soul building enthusiasm for women’s sports, and the Oakland 
					Roots injecting fresh energy into the Coliseum as they make it their new home field. </p>

				<p> But the fans also bring energy and passion back into the stands, proudly rallying behind their teams. 
					For Oakland fans who have endured heartbreak after watching their beloved teams leave the city not once, 
					but three times, this resurgence means even more. </p>	

				<p>	Since announcing their move to the Coliseum, the Oakland Roots have led the United Soccer League (USL) 
					in fan attendance, fueled by an impressive turnout at their home opener. According to data from the USL, 
					more than 44,000 fans have attended Roots games so far this season.</p>

					<!-- ( Code in Jess USL attendance graphic)  -->
				<p>	“If fans believe in you and they know you're honest and telling the truth, and you're showing that 
					you want your teams to be competitive,” Dave Newhouse, a retired Oakland sports columnist, said. 
					"They don't always have to win the championship, but they're competitive. Fans will support you. 
					If you treat them dishonestly, it's like, take a hike. Hit the road, Buster. The dance is over.” </p>
					
				<p>	For Camden Riley, a defender and midfielder for the Roots, staying connected to the Roots supporters 
					is as important as anything that happens on the field. Whether it's before kickoff or after the final 
					whistle, Riley makes sure to engage with fans building bonds that extend far beyond the game. </p>
					
				<p>	His efforts reflect the Roots' mission to stay deeply connected to the Oakland community, especially 
					at a time when local fans are searching for teams that truly represent them and care about their 
					community while offering stability. That commitment has become a defining part of the Roots' identity, 
					setting them apart. </p>
					
				<p>	“I think Oakland fans are the best fans in the world," Riley said. “So after every game, I'm always 
					giving autographs, high fives, you know, hanging out with the fans because we wouldn't be able to play 
					without them. And that's what makes it special.” </p>

				<p>	The fans bring energy not only inside the stadiums, but outside as well, with multiple tailgates 
					creating spaces for people to come together, share food and drinks, and build excitement before 
					heading into the game. </p>

				<p>	Before a recent Roots game in April, crews of dedicated supporters groups met up and mingled with 
					margaritas as they shared their hopes for the game. The Roots were on a bit of a losing streak. One 
					group, the Homegrown Hooligans, emphasized their deep ties to the region, having followed the Roots 
					from field to stadium before they landed at the historic Oakland venue. Another, Los Roots, showed off 
					their merch and prepared to raise custom flags over the stadium’s supporters section. Inside, the Oakland 
					68s, former fans of the A’s, got into position to bang drums and chant over the soccer team’s gameplay. </p>

				<p>	While athletes play for themselves, they also play for the supporters who bring passion, pride, and 
					purpose to every match. </p>

				<p>	Andy Dolich, who spent over 50 years in the sports industry working with different sports leagues, 
					understands the importance of how a team can serve its fans from an executive standpoint, especially 
					looking at the legacy of the A’s. </p>
					
				<p>	“Fans understood that we were committed to the community by improving all of the concessions, by 
					making sure the Coliseum was operating in the cleanest fashion possible, by making sure that parking 
					wasn't a hassle,” Dolich said. “We had the benefit of Bart, people just coming to the Coliseum and hopping 
					off Bart. Walking across the bridge and coming into the ballpark, you know, very few sports teams have that. 
					We did, so we packaged all of that, and it was working for us.” </p>

				<p>	In Oakland, that bond between team and community runs deeper than wins and losses; it's about loyalty, 
					resilience, and pride in where they come from. And as the Roots, Soul, and the Ballers fill the void that 
					was left behind by other franchises, it's the fans who continue to keep Oakland’s spirit alive and thriving. </p>
					
				
				</div>
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
		background: #254441;
		color: white;
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
		color:white;
		padding: 0 1rem;
		text-align: center;
		background-color: #254441;
		border-radius: 2rem;
	}

	.title {
    	font-family: "Mexcellent 3D";
    	font-weight: normal;
    	font-style: normal;
		color: rgb(255, 255, 255);
	}

	.news-container {
		position: relative;
		width: 100%;
		height: 100%;
	}

	.newshead {
		position: absolute;
		/* top: 50%;
		left: 50%
		transform: translate(-50%, -50%); */
		color: white;
		text-align: center;
		height: 160px; 
		transition: all 0.3s ease;
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
		opacity: 75%;
	}

	.shadow {
		box-shadow: 5px 5px 10px 2px rgb(0 0 0 / 0.8);
	}

	.navbar {
		display: flex;
		gap: 10rem;
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
		opacity: 1;
	}

	button.active {
		opacity: 1;
		background-color: #eF3054;
		box-shadow: 6px 6px #2B2118;
	}

	.text {
		text-align: center;
		margin-top: 2rem;
		margin-bottom: 2rem;
	}
	
	.content {
		text-align: left;
		font-size: medium;
		padding: 0 150px;
		font-weight: 50;
	}

	.box {
		background-color: #2e86ab;
		padding: 1.5rem;
		margin: 0;
	}

</style>


<Footer />
