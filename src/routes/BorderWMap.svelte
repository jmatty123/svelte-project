<script>
    import Map from './Map.svelte';
</script>


<div class="w-full h-full flex justify-center items-center">

	<div id="border" class="box-border border-2 border-primary-500 rounded-xl flex justify-center items-center w-4/5 h-4/5 mx-auto">
  
		<div id="mapdiv" class="w-full h-full p-2 text-center overflow-hidden">
			<Map />
		</div>
	
	</div>

</div>