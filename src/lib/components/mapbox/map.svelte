<script lang="ts">
  import MapLibre from 'svelte-maplibre/MapLibre.svelte';
  import LineLayer from 'svelte-maplibre/LineLayer.svelte';
  import { FillLayer } from 'svelte-maplibre';
  import GeoJSON from 'svelte-maplibre/GeoJSON.svelte';
  import Marker from 'svelte-maplibre/Marker.svelte';
  import Popup from 'svelte-maplibre/Popup.svelte';
  import { Legend } from 'layerchart';
  import MarkerData from './../mapbox/ce_revised.csv'
  import type { FeatureCollection } from 'geojson';
  import ZoomRange from 'svelte-maplibre/ZoomRange.svelte';
  import { zoomTransition } from 'svelte-maplibre/expressions.js';
  
  import { scaleThreshold, scaleOrdinal } from 'd3-scale';
    import { count } from 'd3-array';
  
  // geo data
  const queens = 'https://raw.githubusercontent.com/ebrelsford/geojson-examples/master/queens.geojson'
  const nbh = "https://raw.githubusercontent.com/brandendupont-mcw/queens-community-dev/refs/heads/main/src/lib/components/mapbox/nbh.geojson"

  console.log(nbh)


  //geo specs
  let borderColor = '#000000';

  let zoomThreshold = $state(10.1);

</script>

<div class="max-w-[900px] mx-auto mt-4 mb-20 sm:pl-2 sm:pr-2 pl-6 pr-6">
<MapLibre
  style="https://basemaps.cartocdn.com/gl/positron-gl-style/style.json"
  class="relative aspect-[9/16] max-h-[70vh] w-full sm:aspect-video sm:max-h-full"
  center={[-73.814817, 40.672054]}
  zoom={10.0}
  standardControls
>

  <div class="absolute z-50 right-4 top-4 bg-black text-white h-[160px] w-[250px] border-2 border-black p-3 sm:block hidden">
    <div class="border-t border-white mb-2"></div>
    <p class="font-semibold text-lg ">Community Partnerships Division Event Map</p>
    <div class="flex flex-row gap-3 items-center mt-6">
      
      <div class="rounded-full bg-main w-3 h-3 "></div>
      <div class=" text-white  text-md mt-1">
    Represents a Community Event 
      </div>
    </div>

  </div>




  {#each MarkerData as { Longitude, Latitude, Event, Location } }
  {@const lngLat = [Longitude,Latitude]}
  <Marker
    {lngLat}
    class="grid opacity-25 h-2 w-2 place-items-center rounded-full  bg-main text-black shadow-2xl focus:outline-2 focus:outline-black "
    opacity={.8}
  >
    <Popup openOn="hover" offset={[0, -10]}>
      <div class="text-md font-semibold  max-w-[275px]">{Event}</div>
      <div class="text-sm  max-w-[300px]">{Location}</div>
    </Popup>
  </Marker>
  {/each}
  <Marker
    lngLat={[-73.8707, 40.785]}
    class="grid h-8 w-8 place-items-center rounded-full bg-black text-white shadow-2xl focus:outline-2 focus:outline-black"
  >
    <span> LGA </span>
  </Marker>

  <Marker
    lngLat={[-73.790, 40.652]}
    class="grid h-8 w-8 place-items-center rounded-full bg-black text-white shadow-2xl focus:outline-2 focus:outline-black"
  >
    <span> JFK </span>
  </Marker>

  <GeoJSON id="queens" data={queens} >
    <LineLayer
    layout={{ 'line-cap': 'round', 'line-join': 'round' }}
    paint={{ 'line-color': borderColor, 'line-width': 1 }}
  />
  </GeoJSON>

  

</MapLibre>
</div>