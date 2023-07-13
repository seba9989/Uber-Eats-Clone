<script lang="ts">
	interface CityType {
		text: string;
		url: string;
	}

	let cityList: CityType[] = [
		{
			text: 'Białystok',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Białystok',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Białystok',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Białystok',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		},
		{
			text: 'Bydgoszcz',
			url: '/'
		}
	];

	let innerWidth: number;

	let mobileVersion: boolean;

	$: if (innerWidth != undefined) {
		mobileVersion = innerWidth < 500;
		// console.log(mobileVersion);
	}
</script>

<svelte:window bind:innerWidth />

<main>
	<header>
		<h2>Miasta w pobliżu</h2>

		{#if !mobileVersion}
			<a href="/pl/location">Wyświetl wszystkie miasta (ponad 500)</a>
		{/if}
	</header>

	<div class="map">Tu powinna być mapa</div>

	<div class="grid">
		{#each cityList as city}
			<a href={city.url}>{city.text}</a>
		{/each}
	</div>

	{#if mobileVersion}
		<a href="/pl/location" style="margin-top: 24px;">Wyświetl wszystkie miasta (ponad 500)</a>
	{/if}
</main>

<style lang="scss">
	main {
		display: flex;
		flex-direction: column;
	}

	a {
		text-decoration: underline;
	}

	header {
		display: flex;
		justify-content: space-between;

		h2 {
			margin: 0;
			font-weight: 700;
			font-size: 36px;
		}
	}

	.map {
		width: 100%;
		height: 360px;

		margin: 24px 0;

		@media (max-width: 500px) {
			margin: 16px 0;
		}

		display: flex;
		justify-content: center;
		align-items: center;
		background: #afd7fe;
	}

	.grid {
		margin-top: 24px;

		display: grid;
		grid-template-columns: auto auto auto auto;
		grid-row: auto auto auto auto auto auto;

		gap: 24px;

		* {
			font-weight: normal;
			text-decoration: none;
		}
	}
</style>
