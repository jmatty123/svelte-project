<script lang="ts">
    import { onMount } from 'svelte';
    import mapboxgl from 'mapbox-gl';
  
    let mapContainer: HTMLElement;
  
    onMount(() => {
      mapboxgl.accessToken = 'pk.eyJ1Ijoiam1hdHR5MTIzIiwiYSI6ImNsaHNvdXhsdzA2YmkzbW55cWRpcHNrcWgifQ.njIHFQKvVwADOOh9kt8KHA';
  
      const map = new mapboxgl.Map({
        container: mapContainer,
        style: 'mapbox://styles/jmatty123/clhy5k88401g701pf5oo518xx', // the style URL
        center: [-77.0369, 38.8951], // the starting longitude and latitude
        zoom: 9, // the starting zoom
        trackResize: true,
        interactive: false,
        
      });
    });
  </script>
  
  <div class="absolute h-full w-full flex flex-col justify-center items-center text-center box-border">
  <div id="map" class="relative h-full w-full" bind:this={mapContainer}></div>
  </div>