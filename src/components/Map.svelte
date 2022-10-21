<script lang="ts">
	// OpenLayers
	import Map from 'ol/Map';
	import TileLayer from 'ol/layer/Tile';
	import 'ol/ol.css';

	// Svelte
	import View from 'ol/View';
	import OSM from 'ol/source/OSM';

	// Exports
	let mapId = '20';
	// Local state
	let map: Map;

	// functions
	const setupMap = (node: HTMLDivElement) => {
		const osmLayer = new TileLayer({
			source: new OSM()
		});
		map = new Map({
			target: node,
			layers: [osmLayer],
			view: new View({
				center: [0, 0],
				zoom: 2
			})
		});
	};
</script>

<h1>{mapId}</h1>

<div id={mapId} class="map" use:setupMap />

<style>
	.map {
		width: 400px;
		height: 400px;
	}
</style>
