<script lang="ts">
    import { Accordion, AccordionItem } from '@skeletonlabs/skeleton';
</script>

<div class="w-full sm:w-[610px] bg-surface-100-800-token shadow-md">
    <Accordion autocollapse>
        <AccordionItem open class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-thin text-xl">Who?</p></svelte:fragment>
            <svelte:fragment slot="content"><p class="font-thin text-lg">Thanks for visiting my website! My name is Matt. Im an aspiring developer and artist based in the Washington D.C. area. My goal is to leverage technology to create powerful experiences that positively impact the world.</p></svelte:fragment>
        </AccordionItem>
        <AccordionItem class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-thin text-xl">What?</p></svelte:fragment>
            <svelte:fragment slot="content"><p class="font-thin text-lg">This website is my corner of the internet! You will find a portfolio of work and projects I have been involved with. </p></svelte:fragment>
        </AccordionItem>
        <AccordionItem class="text-center">
            <svelte:fragment slot="lead"></svelte:fragment>
            <svelte:fragment slot="summary"><p class="font-thin text-xl">Why?</p></svelte:fragment>
            <svelte:fragment slot="content"><p class="font-thin text-lg pb-2">I created this website to showcase the projects, skills, and techniques ive developed as I learn more about web design and development. Check back often to see what I'm working on!</p></svelte:fragment>
        </AccordionItem>
        <!-- ... -->
    </Accordion>
</div>
