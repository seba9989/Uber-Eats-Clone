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
		<h2>Kraje, w których działa Uber Eats</h2>

		{#if !mobileVersion}
			<a href="/">Zobacz wszystkie kraje</a>
		{/if}
	</header>
	<div class="grid">
		{#each CountriesList as Country}
			<a href={Country.url}>
				{Country.text}
			</a>
		{/each}
	</div>

	{#if mobileVersion}
		<a href="/" style="margin-top: 24px;">Zobacz wszystkie kraje</a>
	{/if}
</main>

<style lang="scss">
	a {
		text-decoration: underline;
	}

	main {
		display: flex;
		flex-direction: column;
	}

	header {
		display: flex;
		justify-content: space-between;
		align-items: center;

		h2 {
			font-size: 36px;
			font-weight: 700;

			margin: 0;
		}
	}

	.grid {
		margin-top: 24px;

		display: grid;
		grid-template-columns: auto auto auto auto;

		@media (max-width: 500px) {
			grid-template-columns: auto auto;
		}

		gap: 24px;

		* {
			font-weight: normal;
		}

		a {
			text-decoration: none;
		}
	}
</style>
