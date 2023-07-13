<script>
	import CitiesNearby from '$lib/components/CitiesNearby.svelte';
	import CountriesWhereUberEatsOperates from '$lib/components/CountriesWhereUberEatsOperates.svelte';
	import FirstFullSide from '$lib/components/FirstFullSide.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Imges from '$lib/components/Imges.svelte';
</script>

<FirstFullSide />

<div class="padding">
	<div class="Link">
		<div>
			<img
				src="https://d3i4yxtzktqr9n.cloudfront.net/web-eats-v2/31ee382bd0e6ed84.svg"
				alt=""
				width="64"
				height="64"
			/>
			<p>W aplikacji na Androida wybór jest jeszcze większy.</p>
		</div>

		<a href="/">
			<svg aria-hidden="true" focusable="false" viewBox="0 0 24 24" height="16" width="16">
				<g>
					<path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M15.297 3.415l-.233.343c1.77.804 2.97 2.326 2.97 4.069H6.341c0-1.743 1.199-3.265 2.97-4.069l-.234-.343-.233-.338-.52-.761a.2.2 0 01.058-.282.214.214 0 01.29.057l.793 1.157.238.348a7.035 7.035 0 012.484-.444c.888 0 1.729.16 2.484.444l1.032-1.505a.21.21 0 01.288-.057.198.198 0 01.059.282l-.52.76-.234.339zm-1.23 2.176c0 .337.28.61.626.61a.618.618 0 00.627-.61.617.617 0 00-.627-.61.617.617 0 00-.627.61zm-4.385.61a.618.618 0 01-.627-.61c0-.338.28-.61.627-.61.346 0 .627.272.627.61 0 .337-.28.61-.627.61z"
					/>
					<path
						d="M6.342 8.639h11.692v8.942c0 .71-.592 1.288-1.322 1.288h-.956c.033.107.052.22.052.338v2.574c0 .673-.562 1.22-1.254 1.22s-1.253-.547-1.253-1.22v-2.574c0-.119.018-.23.05-.338h-2.327c.032.107.051.22.051.338v2.574c0 .673-.562 1.22-1.253 1.22-.692 0-1.254-.547-1.254-1.22v-2.574c0-.119.018-.23.05-.338h-.953c-.73 0-1.323-.578-1.323-1.288V8.639zm-2.089 0C3.561 8.639 3 9.185 3 9.858v5.216c0 .673.56 1.22 1.253 1.22.692 0 1.253-.547 1.253-1.22V9.858c0-.673-.561-1.219-1.253-1.219zM18.87 9.858c0-.673.56-1.219 1.253-1.219.691 0 1.252.546 1.252 1.219v5.216c0 .673-.56 1.22-1.252 1.22-.693 0-1.254-.547-1.254-1.22V9.858z"
					/>
				</g>
			</svg>

			Pobierz aplikację
		</a>
	</div>

	<Imges />
	<CitiesNearby />
	<CountriesWhereUberEatsOperates />
</div>
<div class="link">
	<a href="/">
		Dowiedz się, jak Uber Eats ustala kolejność lokali w kanale. <div>Więcej informacji</div>
	</a>
</div>

<Footer />

<style lang="scss">
	.padding {
		display: flex;
		flex-direction: column;
		gap: 80px;

		padding: 0 40px;

		@media (max-width: 500px) {
			gap: 48px;

			padding: 0 16px;
		}

		.Link {
			@media (min-width: 500px) {
				display: none;
			}

			display: flex;
			flex-direction: column;
			gap: 16px;

			div {
				display: flex;
				gap: 16px;
				align-items: center;

				p {
					font-weight: 700;
					font-size: 24px;
					margin: 0;
				}
			}

			a {
				min-height: 56px;

				display: flex;
				align-items: center;
				justify-content: center;
				gap: 4px;

				white-space: nowrap;

				padding: 12px 16px;

				font-size: 14px;

				background: rgb(238, 238, 238);
				border-radius: 8px;

				&:hover {
					background: rgb(226, 226, 226);
				}
			}
		}
	}

	.link {
		margin-top: 24px;
		display: flex;
		justify-content: center;

		a {
			font-weight: 400;
			display: flex;
			width: fit-content;

			div {
				font-weight: 400;
				text-decoration: underline;
			}
		}
	}
</style>
