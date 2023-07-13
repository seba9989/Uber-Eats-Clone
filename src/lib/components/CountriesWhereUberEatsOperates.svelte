<script lang="ts">
	interface CountryType {
		text: string;
		url: string;
	}

	let CountriesList: CountryType[] = [
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		},
		{
			text: 'Australia',
			url: 'Belgia'
		}
	];
</script>

<h2>Kraje, w których działa Uber Eats</h2>
<div class="grid">
	{#each CountriesList as Country}
		<a href={Country.url}>
			{Country.text}
		</a>
	{/each}
</div>

<style lang="scss">
	h2 {

		font-size: 36px;
		font-weight: 700;
	}

	.grid {
		margin-top: 24px;

		display: grid;
		grid-template-columns: auto auto auto auto;
		grid-row: auto auto auto auto auto auto auto auto;

		gap: 24px;

		* {
			font-weight: normal;
		}
	}
</style>
