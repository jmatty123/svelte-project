<script lang="ts">
    import { Accordion, AccordionItem} from '@skeletonlabs/skeleton';
</script>

<div class="w-full sm:w-[610px] bg-surface-100-800-token shadow-md">
    <Accordion autocollapse>
        <AccordionItem open class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-semibold text-lg">Who?</p></svelte:fragment>
            <svelte:fragment slot="content"><p class="text-lg">Thanks for visiting my website! My name is Matt. Im an aspiring developer and artist based in Washington D.C. My goal is to leverage technology to create powerful experiences that positively impact the world.</p></svelte:fragment>
        </AccordionItem>
        <AccordionItem class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-semibold text-lg">What?</p></svelte:fragment>
            <svelte:fragment slot="content"><p class="text-lg">I created this project to deepen my understanding of web development and design, learn new techniques, and showcase the skills I've picked up along the way! This project is a learning experience and will be under constant development. Check back often to see what I'm working on!</p></svelte:fragment>
        </AccordionItem>
        <AccordionItem class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-semibold text-lg">Why?</p></svelte:fragment>
            <svelte:fragment slot="content"><p class="text-lg">Why not? I can put whatever I want on the internet now.</p></svelte:fragment>
        </AccordionItem>
        <!-- ... -->
    </Accordion>
</div>
