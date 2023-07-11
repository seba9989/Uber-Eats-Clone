<script>
	import CitiesNearby from '$lib/components/CitiesNearby.svelte';
	import FirstFullSide from '$lib/components/FirstFullSide.svelte';
	import Imges from '$lib/components/Imges.svelte';
</script>

<FirstFullSide />

<div class="padding">
	<Imges />
	<CitiesNearby />
</div>

<style lang="scss">
	.padding {
		padding: 0 40px;
	}
</style>
