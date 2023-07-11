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
</script>

<header>
	<h2>Miasta w pobliżu</h2>

	<a href="/pl/location">Wyświetl wszystkie miasta (ponad 500)</a>
</header>

<div class="map">Tu powinna być mapa</div>

<div class="grid">
	{#each cityList as city}
		<a href={city.url}>{city.text}</a>
	{/each}
</div>

<style lang="scss">
	header {
		display: flex;
		justify-content: space-between;

		h2 {
			margin: 0;
			font-weight: 700;
			font-size: 36px;
		}

		a {
			text-decoration: underline;
		}
	}

	.map {
		width: 100%;
		height: 360px;

		margin: 24px 0;

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
		}
	}
</style>
