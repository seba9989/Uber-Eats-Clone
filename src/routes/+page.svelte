<script>
	import CitiesNearby from '$lib/components/CitiesNearby.svelte';
	import CountriesWhereUberEatsOperates from '$lib/components/CountriesWhereUberEatsOperates.svelte';
	import FirstFullSide from '$lib/components/FirstFullSide.svelte';
	import Imges from '$lib/components/Imges.svelte';
</script>

<FirstFullSide />

<div class="padding">
	<Imges />
	<CitiesNearby />
	<CountriesWhereUberEatsOperates />
	<div class="link">
		<a href="/">
			Dowiedz się, jak Uber Eats ustala kolejność lokali w kanale. <div>Więcej informacji</div>
		</a>
	</div>
</div>

<style lang="scss">
	.padding {
		padding: 0 40px;
	}

	.link {
		margin-top: 24px;
		display: flex;
		justify-content: center;

		a {
			font-weight: 400;
			display: flex;
			width: fit-content;
		}

		* {
			font-weight: 400;
			text-decoration: underline;
		}
	}
</style>
