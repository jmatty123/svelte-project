<script>
	import { Avatar } from '@skeletonlabs/skeleton';
	import AboutMenu from '/src/components/AboutMenu.svelte';
</script>


<div class="box-border w-full h-full flex flex-col justify-center items-center p-8 space-y-8">

	<a href="https://www.linkedin.com/in/jmatty123/">
		<Avatar cursor="cursor-pointer"
		src="https://media.licdn.com/dms/image/D4E03AQF2w8D3R9HUfg/profile-displayphoto-shrink_800_800/0/1684272249639?e=1691020800&v=beta&t=JhaTiP6FfjBy3X3Tkar-q_acBEziyemUMEy1n5P69IQ"
		initials="MY" width="w-40" class="hover:scale-110 duration-100 shadow-lg" rounded="rounded-full" />
	</a>

	<AboutMenu />

</div>



