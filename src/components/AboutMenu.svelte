<script lang="ts">
    import { Accordion, AccordionItem} from '@skeletonlabs/skeleton';
</script>

<div class="w-5/6 md:w-[650px] bg-surface-100-800-token">
    <Accordion autocollapse>
        <AccordionItem open class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-semibold text-lg">Who?</p></svelte:fragment>
            <svelte:fragment slot="content"><p>Thanks for visiting my website! My name is Matt. Im an aspiring developer with certifications in responsive web design, Javascript, and database administration. My goal is to leverage technology in a way that positively impacts the world.</p></svelte:fragment>
        </AccordionItem>
        <AccordionItem class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-semibold text-lg">What?</p></svelte:fragment>
            <svelte:fragment slot="content"><p>I created this project to deepen my understanding of web development and design, learn new techniques, and showcase the skills I've picked up along the way! This project is a learning experience and will be under constant development. Check back often to see what I'm working on!</p></svelte:fragment>
        </AccordionItem>
        <AccordionItem class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-semibold text-lg">Why?</p></svelte:fragment>
            <svelte:fragment slot="content"><p>Why not? I can put whatever I want on the internet now.</p></svelte:fragment>
        </AccordionItem>
        <!-- ... -->
    </Accordion>
</div>
