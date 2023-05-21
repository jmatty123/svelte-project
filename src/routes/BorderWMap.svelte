<script>
    import Map from './Map.svelte';
</script>

<div id="border" class="box-border border-2 border-white rounded-xl flex flex-col justify-between items-center space-y-4 h-2/3 m-10">

	<p id="content" class="text-center font-serif font-medium text-white pt-4 px-5">
		This page was built using <a id="svelteLink" class="underline visited:text-gray-300 active:text-gray-500" href="https://svelte.dev/">Svelte</a>
		by <a id="linkedinLink" class="underline visited:text-gray-300 active:text-gray-500" href="https://www.linkedin.com/in/jmatty123/">Matthew Young.</a>
		<br>This project is a learning experience and will be under constant development. Check back regularly!
	</p>
  
	<div id="mapdiv" class="w-full px-4 h-full overflow-hidden">
		<Map />
	</div>
  
	<p id="changelog" class="text-center font-mono text-xs text-white pb-4">
		Creation: 5/16/23 | Latest update: 5/21/23 "fix: map response / adjust: navbar"</p>
	
</div>
