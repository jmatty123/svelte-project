<script>
    import { Accordion, AccordionItem, LightSwitch } from '@skeletonlabs/skeleton';
</script>

<div class="w-5/6 lg:w-1/3 variant-ringed-surface">
<Accordion autocollapse>
	<AccordionItem open>
		<svelte:fragment slot="lead"></svelte:fragment>
		<svelte:fragment slot="summary"><p class="font-semibold text-lg">Who?</p></svelte:fragment>
		<svelte:fragment slot="content">Thanks for visiting my website! My name is Matt. Im an aspiring developer with certifications in responsive web design, Javascript, and database administration. My goal is to leverage technology in a way that positively impacts the world.</svelte:fragment>
	</AccordionItem>
	<AccordionItem>
		<svelte:fragment slot="lead"></svelte:fragment>
		<svelte:fragment slot="summary"><p class="font-semibold text-lg">What?</p></svelte:fragment>
		<svelte:fragment slot="content">I created this project to deepen my understanding of web development and design, learn new techniques, and showcase the skills I've picked up along the way! This project is a learning experience and will be under constant development. Check back often to see what I'm working on!</svelte:fragment>
	</AccordionItem>
    <AccordionItem>
		<svelte:fragment slot="lead"></svelte:fragment>
		<svelte:fragment slot="summary"><p class="font-semibold text-lg">Why?</p></svelte:fragment>
		<svelte:fragment slot="content">Why not? I can put whatever I want on the internet now.</svelte:fragment>
	</AccordionItem>
	<!-- ... -->
</Accordion>
</div>

<p class="text-center font-mono text-[10px] px-20 mt-10">
    Creation: 5/16/23 | Latest update: 5/24/23
</p>



