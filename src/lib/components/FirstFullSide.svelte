<script lang="ts">
	type Delivery = 'now' | 'later';
	type DeliveryDate = {
		data: {
			day: number;
			month: number;
			year: number;
		};
		time: {
			hour: number;
			minutes: number;
		};
	};

	let deliveryType: Delivery = 'now';

	let deliveryDate: DeliveryDate;
</script>

<main>
	<div>
		<h1>Zamów jedzenie pod drzwi</h1>
		<div class="search-bar">
			<div class="text-input">
				<span class="material-symbols-outlined"> location_on </span>
				<input type="text" placeholder="Wpisz adres dostawy" />
			</div>

			<button class="select-menu">
				<span class="material-symbols-outlined icon"> schedule </span>

				{#if deliveryType === 'now'}
					<p>Dostarcz teraz</p>
				{:else if deliveryDate}
					<p>
						{deliveryDate.data.day}-{deliveryDate.data.month}-{deliveryDate.data.year},
						{deliveryDate.time.hour}:{deliveryDate.time.minutes}
					</p>
				{/if}

				<span class="material-symbols-outlined icon"> expand_more </span>
			</button>

			<button class="submit"> Wyszukaj restauracje </button>
		</div>
	</div>

	<div class="info">
		<a href="/login">Zaloguj się</a>, aby korzystać z ostatnich adresów
	</div>
</main>

<style lang="scss">
	main {
		height: 100vh;
		background: url('/background.png') center center / cover no-repeat;
		background-size: cover;

		display: flex;
		flex-direction: column;
		justify-content: center;

		padding: 0 40px;

		margin-bottom: 80px;

		h1 {
			margin-bottom: 40px;

			font-size: 52px;
			font-weight: 700;
			line-height: 64px;
		}

		.search-bar {
			display: flex;
			gap: 8px;

			* {
				font-size: 1rem;
			}

			.text-input {
				width: 540px;
				height: 56px;

				display: flex;
				align-items: center;
				gap: 16px;

				padding: 8px 16px;

				border: medium none;

				background-color: #fff;

				line-height: 24px;
				font-size: 16px;

				box-shadow: rgb(238, 238, 238) 0px -1px 0px inset;

				input {
					height: 100%;
					width: 100%;

					border: none;
					font-weight: normal;

					&:focus {
						outline: 0;
					}
				}
			}

			.select-menu {
				display: flex;

				background-color: #fff;

				padding: 4px;

				box-shadow: rgb(238, 238, 238) 0px -1px 0px inset;

				align-items: center;

				p {
					margin: 0;
				}

				.icon {
					aspect-ratio: 1/1;
					height: 48px;

					display: flex;
					justify-content: center;
					align-items: center;
				}
			}

			.submit {
				border-radius: 8px;
				font-size: 18px;
				color: #fff;

				background: #000;

				padding: 12px 16px;

				&:hover {
					background: rgb(51, 51, 51);
				}
			}
		}

		.info {
			a {
				text-decoration: underline;
			}
			margin-top: 24px;
		}
	}
</style>
