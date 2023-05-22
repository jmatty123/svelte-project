<script lang="ts">
    import { onMount } from 'svelte';
    import mapboxgl from 'mapbox-gl';
  
    let mapContainer: HTMLElement;
  
    onMount(() => {
      mapboxgl.accessToken = 'pk.eyJ1Ijoiam1hdHR5MTIzIiwiYSI6ImNsaHNvdXhsdzA2YmkzbW55cWRpcHNrcWgifQ.njIHFQKvVwADOOh9kt8KHA';
  
      const map = new mapboxgl.Map({
        container: mapContainer,
        style: 'mapbox://styles/mapbox/dark-v11', // the style URL
        center: [-77.0369, 38.9072], // the starting longitude and latitude
        zoom: 11 // the starting zoom
      });
    });
  </script>
  
  <div id="map" class="h-full w-full" bind:this={mapContainer}></div>