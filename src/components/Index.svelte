<script>
	import Hero from "$components/helpers/Hero.svelte";
	import Footer from "$components/Footer.svelte";
	import Scrolly from "$components/helpers/Scrolly.svelte";
	import {fade} from 'svelte/transition';
	import Video from "$components/helpers/Video.svelte";
	import Image from "$components/helpers/Image.svelte";
	import Page from "../routes/+page.svelte";

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
					<h1 class="title" style:font-size={"12.5rem"} style:line-height={"1"} style:padding={"0 1.5rem"}
					style:margin-top={"3.5rem"} style:margin-bottom={"1rem"}>OAKTOWN</h1>
					<h6 style:margin-bottom={"2rem"} style:text-wrap-style="balance">A city once spoiled with championship 
						teams is learning to rebuild its sports scene from the 'roots' up.</h6>
					<p style:margin-bottom={"3.5rem"}>By Marquis Chambers, Riley Ramirez, Jessica Blough and Daniela Sandoval</p>
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

	<div class="box" style:margin={"0"}>
	</div>

	{#if selected}
		<section class="dynamic-content" style:padding-top={"0"}>
			{#if selected === 'roots'}
			<section class="hero-container">
				<Video class="hero" src="demo/assets/videos/Fansvideo2.mov"
					alt="Roots"
					autoplay={true}
					loop={true} />
				<h1 class="hero-header" style:font-size={"6.5rem"} style:text-align="center">The Roots</h1>
			</section>
				<div class="content"  style:margin-top={"2rem"}>
					<!-- <h2 class="title" style:font-size={"7rem"} style:text-align="center">The Roots</h2> -->
					<p>The Oakland Coliseum, briefly dormant, came alive again when the Oakland Roots announced 
						at the start of this season that they would claim the Oakland Coliseum as their home field.
						 While it was planned as a short term focus for the Roots, the team has shifted their focus 
						 to the Coliseum becoming their permanent home field. </p>
						
					<p>	The Oakland community was left heartbroken in April 2024 when the Oakland Athletics — whose 
						slogan read “Rooted in Oakland” — announced they would be uprooted to Sacramento for their 
						2025 season. They’ll play at Sutter Health Park in West Sacramento until 2027 while they wait 
						for their new stadium in Vegas to be built.   </p>
				
				<div class="grid" style:padding-bottom={"2rem"}>	
					<div>
					<p>	But the Roots have revitalized the spirit of the community by bringing a refreshing and 
						much-needed sense of energy back into the local sports scene. Their exciting, gritty style of 
						play resonates deeply with Oakland residents, reflecting the same toughness and resilience 
						that fans have long associated with teams that played at the Coliseum. </p>
						
					<p>	In 1964, Dave Newhouse, fresh out of college with a journalism degree, landed a job at the 
						<i>Oakland Tribune</i>. Over a career that spanned nearly five decades before his retirement in 2011, 
						Newhouse developed a deep understanding of the Oakland community.</p>
					
					<p>	“But one thing about Oakland, it's feisty,” Newhouse said. “You know, It may not be 
						recognized, but it's feisty and it battles.” </p>
					</div>
				<div style:height={"87%"}>
					<Image src="demo/assets/images/roots-game-zoomed.png" alt="April 19 Roots Game" 
					caption="Roots beat the Orange County SC 2-0 at their April 19 game. Photo credit: Jessica Blough" />
				</div>
				</div>

					<p>	Whether it was the hard nosed style of the Raiders, the fearless attitude of the A’s, or 
						the passionate intensity of the Warriors, Oakland sports have always embodied a sense of pride, 
						perseverance, and authenticity. </p>
						
					<p>	The Roots, a USL team founded in Oakland in 2018, continue that tradition, offering the community 
						a team that mirrors its identity: hardworking, fearless, and proud. Their presence goes beyond just 
						what happens on the field; they have reconnected the city with a sense of belonging and hope at a 
						time when the loss of other major teams left a void in Oakland’s sporting landscape.  </p>
						
					<p>	Camden Riley, defender and midfielder for the Roots, knows how important it is for him and the club 
						to be active in the community. </p>
						
					<p>	“I commonly am in the community going to soccer practices, trying to help out kids 
						and try and just grow a passion for the game,” Riley said. “Whether it be soccer or 
						another sport in Oakland.” </p>
						
					<p>	Riley’s presence along with the Roots at local practices is about more than just teaching a sport; 
						it's about nurturing dreams in a city that has always fought to keep them alive. By inspiring kids 
						to find their passion, they are helping to build a future where sports are not just an outlet, but 
						a lifeline.</p>
						
					<p>	In Oakland, where grit and heart have always been part of the fabric, leaders Riley remind individuals 
						that true change begins in the small moments. In many ways, the Roots are not just playing soccer: 
						they are carrying on a cultural legacy that has defined Oakland sports for generations.</p>
					
					<Video src="demo/assets/videos/roots-riley.mp4" alt="Camden Riley Interview"
						poster="demo/assets/images/roots-thumbnail.jpeg"
						caption="Video by Marquis Chambers, Jessica Blough and Daniela Sandoval"/>
						
				</div>

			{:else if selected === 'city'}
				<div class="content" style:margin-top={"0"}>
					<h2 class="title" style:font-size={"6.5rem"} style:text-align="right" style:margin-bottom={"0"}
					style:margin-top={"0"}>The City</h2>
					<Image src="demo/assets/images/dave-still.jpg" alt="Dave Newhouse" />
					<h2>Meet Dave Newhouse!</h2>
					<p> After covering Oakland sports for 60 years, former <i>Oakland Tribune</i>  sports columnist Dave Newhouse 
						(86) came out of retirement to co-author "Goodbye, Oakland: Winning, Wanderlust, and a Sports 
						Town's Fight for Survival." In their book, Dave and former sports executive Andy Dolich explore 
						the history of professional sports in Oakland and how it has shaped the city's identity. 
						We spoke to Dave to learn more about the different eras of Oakland sports and understand how the city 
						has gotten to where it is today. </p>
					<p><strong style:color={"#FCE354"}>Click</strong> on the decades below 
						to learn about Oakland's sports history and hear stories from Dave!</p>

					<details>
						<summary>1900s - The Beginning of a Sports Town</summary>
						<p>Oakland becomes a sports town in 1903 with Oakland Oaks, a minor league baseball team in the Pacific
							Coast League who played in the city until 1955. </p>

						<Video src="demo/assets/videos/Dave/Dave-1903.mp4" alt="Oakland became a sports town in 1903." />
					</details>
					<details>
						<summary>1960s - Raiders and Athletics Move In</summary>
						<p>In 1960, the Raiders moved to Oakland. Two years later, the City of Oakland and Alameda County 
							approved the $25 million project to build the Coliseum complex, which would become the home of 
							the Raiders. While the team waited for the Coliseum to be built, they played briefly at Kezar 
							Stadium, Candlestick Park, and Frank Youell Field. After legal battles delayed construction for two 
							years after it was approved, the Coliseum was officially complete by 1966. </p>
						
						<Video src="demo/assets/videos/Dave/Dave-1960s.mp4" alt="The Raiders are the first major pro team to be
						established in Oakland." />

						<p>Al Davis became head coach of the Oakland Raiders in 1963, evolving from a struggling team into an AFL 
							powerhouse that won the 1967 championship and appeared in Super Bowl II. </p>

						<p>The Athletics, founded in 1901 by Connie Mack, became a powerhouse team in Major League Baseball, 
							winning multiple World Series titles while based in Philadelphia until 1954, when businessman Arnold 
							Johnson purchased the team and relocated it to Kansas City. Later led by owner-manager Charles O. 
							'Charlie' Finley, the A’s struggled near the bottom of the American League, finishing last in both 
							1960 and 1967 before relocating to Oakland in 1968. After the move, Finley sought a larger stadium 
							and a bigger market, marking the beginning of Oakland Athletics.</p>

						<p>"The experience at the Coliseum was unlike anything you've ever seen," Dave said. "It was like Mardi Gras.
							People came in costumes. I saw guys walking on stilts."</p>
						
						<p>Finley also owned professional NHL hockey the California Golden Seals team that played at the Oakland 
							Alameda County Coliseum Arena from 1967 to 1976. </p>
							
						<p>Despite the excitement of a new franchise, the team struggled both on the ice and at the box office, 
							dealing with poor attendance, limited success, and frequent ownership changes. Over the years, 
							the Seals became known for their colorful uniforms and name changes. </p>

 						<p>In 1976, the franchise relocated to Cleveland, marking the end of NHL hockey in the East Bay.</p>

					</details>
					<details>
						<summary>1970s - A Golden Age of Oakland Sports</summary>
						<p>Throughout the 1970’s, the Raiders were a dominant NFL force, led by coach John Madden and stars like 
							Ken Stabler, Fred Biletnikoff, and Willie Brown. They were in regular championship contention and won 
							Super Bowl XI in 1977. </p>

						<p>The Golden State Warriors moved to Oakland in 1971 and rose to prominence later that decade, culminating 
							in their first NBA championship in the 1974–75 season. </p>
						
						<div class="dave-container">
							<Video class="dave" src="demo/assets/videos/Dave/Dave-1975Warriors.mp4" 
								alt="Dave on Warriors 1975"/>
							<h3 class="dave-text">The 1975 Warriors</h3>
						</div>
					
						<div class="grid" style:padding-top={"1rem"} style:padding-bottom={"0.5rem"}>
						<p style:padding-left={"1.5rem"}>Nicknamed the 'Swingin' A's,' the Oakland Athletics dominated baseball in the 1970s, winning three 
							straight World Series championships from 1972 to 1974 and capturing five consecutive American League 
							West Division titles between 1971 and 1975. </p>

						<div class="youtube-video">
							<iframe width="100%" height="300" src="https://www.youtube.com/embed/niqLDoHkfbg?si=4q0kJfWXlKuMzGe6" 
							title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; 
							encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" 
							allowfullscreen></iframe>
							<p class="caption">Credit: <a href="https://www.youtube.com/watch?v=niqLDoHkfbg" class="link">AP Archive</a>, 
								1972 Oakland A's World Series Champions Parade</p>
						</div>
						</div>

					</details>
					<details>
						<summary>1980s - Henderson, McGwire, Eckersley and 'Billy Ball'</summary>
						<p>Led by head coach Tom Flores, the Oakland Raiders enjoyed a strong run in the early 1980s, winning 
							Super Bowl XV in 1980, and after relocating to Los Angeles in 1982, continued their success with a
							 victory in Super Bowl XVIII in 1984.</p>

						<p>The Oakland A's were also a strong team in these years, featuring stars like Rickey Henderson, Mark 
							McGwire, and Dennis Eckersley, making three consecutive World Series appearances from 1988 to 1990, 
							including a Bay Area showdown victory against the Giants in 1989, while also experiencing significant
							managerial changes, such as Billy Martin’s leadership in 1980, which introduced 'Billy Ball'. </p>
						
						<div class="youtube-video">
							<iframe width="100%" height="450" src="https://www.youtube.com/embed/3OJ9IlKn9w4?si=pN9yxiS0lqvB11Sv" 
							title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; 
							encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" 
							allowfullscreen></iframe>
							<p class="caption">Credit: <a href="https://www.youtube.com/watch?v=3OJ9IlKn9w4" 
								class="link">MLB</a>, 
								Rickey Henderson leads off Game 4 of the World Series with a home run to give the Athletcs an early 
								lead over the Giants. Oct. 28, 1989.</p>
						</div>

						<p>Walter A. Haas Jr. acquired ownership of the A's from Charles Finley at the beginning of the decade. 
							“The Haas family was the most wonderful sports ownership. They bought the A’s and all of a sudden 
							there was this family atmosphere at the Coliseum,” Dave said. </p>

						<p>During the 1980s, the Golden State Warriors underwent significant change and development, transitioning 
							from one era of star power with players like Rickey Brown, Joe Barry Carroll, and World B. Free to a 
							new generation of young talent, though the decade did not bring championship success.</p>

					</details>
					<details>
						<summary>1990s - 'Run TMC' and the Raiders Return</summary>
						<p>The 'Run TMC' era defined the Warriors in the early 1990s, with the dynamic trio of Chris Mullin, 
							Mitch Richmond, and Tim Hardaway leading a high-scoring, fast-paced offense that helped the team 
							reach the playoffs multiple times, including a run to the Western Conference Semifinals in 1990-91, 
							though instability and changes in personnel and coaching followed. </p>

						<div class="youtube-video">
							<iframe width="100%" height="500"
							src="https://www.youtube.com/embed/JqzWUxtukbA?si=cBNr8tKDMMDh-fWT" 
							title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; 
							encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" 
							allowfullscreen></iframe>
							<p class="caption">Credit: <a href="https://www.youtube.com/watch?v=JqzWUxtukbA" class="link">NBA</a>, 
								Run TMC's High-Scoring Offense</p>
						</div>

						<p>The Oakland Athletics of the 1990s, after a strong start that saw them reach the World Series in 1990 
							and come close again in 1992, experienced a significant decline marked by a string of losing seasons 
							and key player departures, leading to a period of rebuilding. This included the sale of the team from 
							the Haas family to Ken Hofmann and Steve Schott. </p>

						<p>In 1995, the Raiders returned home to Oakland after a challenging period in Los Angeles, marked by a 
							coaching change and a decline in performance. In agreeing to return, Raiders owner and former head 
							coach Al Davis negotiated that the city increase the Coliseum’s capacity. As a result, the Coliseum 
							built a tower of bleachers known as Mount Davis, restricting the once iconic view of Oakland from 
							inside the stadium. </p>

					</details>
					<details>
						<summary>2000s - 'Moneyball' and New Ownership</summary>
						<div class="grid" style:padding-bottom={"1rem"}>
							<div>
								<p>The 2002 “Moneyball” season became legendary when the Oakland A’s defied the odds, rattling off 20 
									straight wins and proving that grit, strategy, and data could shake the foundations of baseball. 
									Their record-breaking streak captivated fans and rewrote the blueprint for success in Major League Baseball. </p>

								<p>While inspiring a generation of teams to rethink talent evaluation and showing that heart and innovation 
									could rival deep-pocketed franchises. It wasn’t just about the wins — it was about reshaping the game’s 
									future and leaving an enduring legacy on and off the field. </p>
								
								<p>In 2005 John Fisher and his business partner Lew Wolf would buy the Oakland A’s and shortly after will 
									begin searching for a new home for the organization. </p>
							</div>
							<div class="youtube-video" style:height={"100%"}>
								<iframe width="100%" style:height={"90%"} src="https://www.youtube.com/embed/lUVlSwQ9tSU?si=3d30r-xzGZgnHq1V" 
								title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; 
								gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
								<p class="caption">Credit: <a href="https://www.youtube.com/watch?v=lUVlSwQ9tSU" 
									class="link">MLB</a>, Hatteberg hits walk-off homer, A's win 20th straight game. Sept. 4, 2002.</p>
							</div>

						</div>

						<Video src="demo/assets/videos/Dave/Dave-Fisher.mp4" alt="John Fisher dismantled the A's." />
					</details>
					<details>
						<summary>2010s - The Exodus Begins</summary>
							<p>In the 2010s, Oakland sports experienced a resurgence led by the Golden State Warriors, who brought home NBA 
								championships in 2015, 2017, and 2018 and electrified the city and its fans. </p>

							<p>That same era saw the birth of the Oakland Roots in 2018, a soccer club built on community passion and local pride. </p>

							<p>Yet by 2019, heartbreak returned when the Raiders announced their relocation and the Warriors played their final game 
								at Oracle Arena before their move to San Francisco, marking the end of chapter. </p>
							
							<div class="youtube-video">
								<iframe width="100%" height="415" src="https://www.youtube.com/embed/LAP38SwoQKs?si=bwP1m04nIv8nDcg3" 
								title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; 
								encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" 
								allowfullscreen></iframe>
								<p class="caption">Credit: <a href="https://www.youtube.com/watch?v=LAP38SwoQKs" 
									class="link">CBS News</a>, Oakland Raiders Fans Disappointed by Team's Move. March 28, 2017.</p>
							</div>

							<p>The Warriors played their final home game at Oracle Arena on April 7, 2019, before officially moving to Chase 
								Center, which opened September 6, 2019.  </p>

							<p>As for the A's, the organization began talks of building a new stadium at Howard Terminal with the city back in 2018,
								leaving fans believing the team was committed to staying in Oakland. </p>

					</details>
					<details>
						<summary>2020-2024 - The Fall of the Coliseum Empire</summary>
							<h6>2020 - Global Covid-19 Pandemic </h6>
								<p>Like every team worldwide, Oakland sports were hit hard by the global pandemic in 2020, which shut down stadiums 
									and disconnected fans from their teams.</p>
							<h6>2021</h6>
								<p>Starting with the 2021 season, owner John Fisher slashed the Oakland A’s payroll and traded away key stars like 
									Matt Olson, Matt Chapman, and Sean Manaea, signaling a shift away from competitive ambitions. </p>
								
								<div class="youtube-video">
									<iframe width="100%" height="450" src="https://www.youtube.com/embed/lKtvBF7wPFI?si=tQQisZN5L6XIU5IQ&amp" 
									title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; 
									gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
									<p class="caption">Credit: <a href="https://www.youtube.com/watch?v=lKtvBF7wPFI" 
										class="link">NBC Sports</a>, A's take an important step forward in Howard Terminal ballpark plans. Dec. 17, 2021.</p>
								</div>
							<h6>2022</h6>
								<p>In 2022, the Warriors triumphantly returned to championship form, winning another NBA title — this time in San Francisco.
									Meanwhile, attendance at the Coliseum plummeted, and fan frustration with Fisher’s lack of investment and commitment to 
									Oakland reached a boiling point.  </p>
							<h6>2023</h6>
								<p>In 2023, the Oakland Soul kicked off their inaugural season in the USL W League in 2023, becoming Oakland’s first major 
									women’s team. The team quickly became a symbol of pride and opportunity for the city, drawing strong local support alongside 
									the Oakland Roots.  </p>

								<p>In 2023 and 2024, the A’s posted one of the league’s worst records and secured MLB approval to relocate to Las Vegas, 
									cementing Fisher’s role in the franchise’s decline and departure. </p>

							<div class="grid">
								<div>
									<h6>2024</h6>
									<p>In April 2024, after talks of a new stadium at Howard Terminal fell through, the Athletics announced they would move to 
										Las Vegas by the 2028 MLB season and abandon the Coliseum at the end of the season. 
										The team will play at Sutter Health Park in West Sacramento from 2025 to 2027 until their Vegas 
										ballpark is ready.</p>

									<p>The Oakland Roots revealed plans to play their 2025 season at the historic Coliseum, keeping 
										local soccer alive in the city. </p>

									<p>The Pioneer League baseball team the Oakland Ballers were formed, adding a fresh energy to the city’s 
										sports landscape.  </p>
								</div>
								<div class="youtube-video" style:height={"75%"} style:margin-bottom={"2rem"}>
									<iframe width="100%" height="100%" src="https://www.youtube.com/embed/mOV4vo1eo1M?si=-gapE1tbgRmN44v1&amp;start=109" 
									title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; 
									gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
									<p class="caption">
										Credit: <a href="https://www.youtube.com/watch?v=mOV4vo1eo1M" 
										class="link">ABC7 News</a>, Larry Beil rips into A's owner John Fischer for his letter to Oakland fans. Sept. 23, 2024.</p>
								</div>
							</div>
					</details>
					<details>
						<summary>2025-Present - The Future of Oakland Sports</summary>
							<p>Even after heartbreak and past team departures, the Oakland Ballers are still playing at Raimondi Park. The Oakland Roots play 
								at the Coliseum, and the Oakland Soul play at Merritt College with a special game to take place at the Oakland Coliseum. </p>

							<p>Oakland’s proud sports spirit not only survives, it's building a bright, diverse future for the city’s fans and communities. </p>

							<Video src="demo/assets/videos/Dave/Dave-Misrepresented.mp4" alt="The Comeback Kid"/>
					</details>
					  
				</div>

			{:else if selected === 'fans'}
				<div class="content" style:padding-top={"1rem"}>
					<div class="grid" style:grid-column-gap={"75px"} style:margin-bottom={"1rem"}>
						<div class="group" style:padding-left={"0.5rem"}>
							<h2 class="title" style:font-size={"6rem"} style:text-align="left" 
							style:margin-bottom={"2rem"} style:margin={"0"} style:white-space={"nowrap"}>The Fans</h2>
							<p>A new chapter is unfolding for Oakland sports fans across three teams: 
								the Oakland Ballers bringing baseball to Raimondi Park, the Oakland 
								Soul building enthusiasm for women’s sports, and the Oakland Roots injecting 
								fresh energy into the Coliseum as they make it their new home field. </p>

							<p> But the fans also bring energy and passion back into the stands, proudly 
								rallying behind their teams. For Oakland fans who have endured heartbreak 
								after watching their beloved teams leave the city not once, but three times, 
								this resurgence means even more. </p>

							<p>	Since announcing their move to the Coliseum, the Oakland Roots have led the 
								United Soccer League (USL) in fan attendance, fueled by an impressive turnout 
								at their home opener. According to data from the USL, more than 44,000 fans 
								have attended Roots games so far this season.</p>

							<p>	“If fans believe in you and they know you're honest and telling the truth, and you're showing that 
								you want your teams to be competitive,” Dave Newhouse said. 
								"They don't always have to win the championship, but they're competitive. Fans will support you. 
								If you treat them dishonestly, it's like, take a hike. Hit the road, Buster. The dance is over.” </p>
						</div>
						<div class="video-wrapper" style:max-width={"98%"}>
							<Video
								src="demo/assets/videos/rootsfans.mov"
								alt="Roots Fan Video" 
								caption="Video by Jessica Blough, Marquis Chambers and Daniela Sandoval"
								controls
								hasBorder={true}/>
						</div>
					</div>		
					
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
				
				<div class="chart-wrapper">
					<iframe title="Top USL Attendance, 2025" aria-label="Stacked Bars" id="datawrapper-chart-IxtZZ" 
					src="https://datawrapper.dwcdn.net/IxtZZ/1/" scrolling="no" frameborder="0" style="width: 0; 
					min-width: 100% !important; border: none;" height="482" data-external="1"></iframe>
				</div>
				
				<p>	Before a recent Roots game in April, crews of dedicated supporters groups met up and 
					mingled with margaritas as they shared their hopes for the game. The Roots were on a 
					bit of a losing streak. One group, the Homegrown Hooligans, emphasized their deep ties to 
					the region, having followed the Roots from field to stadium before they landed at the historic 
					Oakland venue. Another, Los Roots, showed off their merch and prepared to raise custom flags 
					over the stadium’s supporters section. Inside, the Oakland 68s, former fans of the A’s, got 
					into position to bang drums and chant over the soccer team’s gameplay. </p>

				<p>	While athletes play for themselves, they also play for the supporters who bring passion, pride, 
					and purpose to every match. </p>

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
		position: absolute;
		background-color: #254441;
		border-radius: 100%;
		box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3), 0 0 20px rgba(255, 255, 255, 0.1);
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
		padding-top: 2rem;
		padding-bottom: 2rem;
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
		padding: 0 350px;
		margin: auto;
		font-weight: 100;
	}

	.box {
		background-color: #2e86ab;
		padding: 1.5rem;
		margin: 0;
	}

	.chart-wrapper {
		margin: 2rem;
		align-content: center;
		background-color:white;
		padding: 2rem;
		display: flex;
	}

	.row {
		display: flex; 
		gap: two elements;
		width: 100%;
	}

	.image-container {
		flex: 2; /* Make image take up more space */
	}

	.text-container {
		flex: 1; /* Make text take up less space */
	}

	.timeline {
		margin-top: 3rem;
	}

	@media (max-width: 600px) {
  		.video {
    	flex-direction: column;
  		}
	}

	.hero-container {
		position: relative;
		width: 100%;
		height: auto;
	}

	.hero-header {
		position: absolute;
		top: 10%;
		left: 50%;
		transform: translate(-50%, -50%);
		color: white;
		font-size: 5rem;
		font-family: "Mexcellent 3D";
		font-size: 7rem;
		text-align: center;
		z-index: 2;
	}

	details {
		border: 1px solid #aaa;
		border-radius: 4px;
		padding: 0.5em 0.5em 0;
	}

	summary {
		font-weight: 500;
		font-size: large;
		margin: -0.5em -0.5em 0;
		padding: 1em;
		background-color: #1b3130;
		border: 1px solid #c5c5c5;
	}

	details[open] {
		padding: 0.5em;
		color: black;
		background-color: white;
	}

	details[open] summary {
		border-bottom: 1px solid #c5c5c5;
		margin-bottom: 0.5em;
		background-color:#15BA7D;
	}

	.dave-text {
		position: absolute;
		padding: 0.2rem;
		top: 3%;
		left: 12%;
		transform: translate(-50%, -50%);
		color: #FCE354;
		background-color: #2e86ab;
		font-size: 1.3rem;
		text-align: left;
		z-index: 2;
	}

	.dave-container {
		position: relative;
		width: 100%;
		height: auto;
	}

	.grid {
		display: grid;
		place-items: center;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 1rem;
	}

	.video-wrapper {
		width: 400;
		max-width: 100%;
		max-height: 500;
	}

	.caption {
		font-size: 0.9rem;
		color: black;
		margin-top: 0.5rem;
		margin-bottom: 0;
	}

	.link {
		color: rgb(0, 101, 224);
		text-decoration: underline;
	}

</style>


<Footer />
