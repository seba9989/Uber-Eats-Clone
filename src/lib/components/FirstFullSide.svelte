<script lang="ts">
	import { dataForm } from '$lib/ts/Stores';

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

	let listOpen = false;
</script>

<main>
	<div>
		<h1>Zamów jedzenie pod drzwi</h1>
		<div class="search-bar">
			<div class="text-input">
				<span class="material-symbols-outlined"> location_on </span>
				<input type="text" placeholder="Wpisz adres dostawy" />
			</div>

			<button class="select-menu" on:click={() => (listOpen = !listOpen)}>
				{#if deliveryType === 'now'}
					<svg
						width="20px"
						height="20px"
						fill="none"
						viewBox="0 0 24 24"
						xmlns="http://www.w3.org/2000/svg"
						aria-hidden="true"
						focusable="false"
					>
						<path
							d="M12 2.83398C6.91671 2.83398 2.83337 6.91732 2.83337 12.0007C2.83337 17.084 6.91671 21.1673 12 21.1673C17.0834 21.1673 21.1667 17.084 21.1667 12.0007C21.1667 6.91732 17.0834 2.83398 12 2.83398ZM17 13.6673H10.3334V5.33398H12.8334V11.1673H17V13.6673Z"
							fill="currentColor"
						/>
					</svg>
					<p>Dostarcz teraz</p>
				{:else if deliveryDate}
					<p>
						<svg
							width="20px"
							height="20px"
							fill="none"
							viewBox="0 0 24 24"
							xmlns="http://www.w3.org/2000/svg"
							aria-hidden="true"
							focusable="false"
						>
							<path
								fill-rule="evenodd"
								clip-rule="evenodd"
								d="M21.1666 8.66732V5.33398H18.6666V2.83398H16.1666V5.33398H7.83325V2.83398H5.33325V5.33398H2.83325V8.66732H21.1666ZM21.1666 21.1673H2.83325V10.334H21.1666V21.1673ZM8.66658 13.6673H6.16658V16.1673H8.66658V13.6673Z"
								fill="currentColor"
							/>
						</svg>
						{deliveryDate.data.day}-{deliveryDate.data.month}-{deliveryDate.data.year},
						{deliveryDate.time.hour}:{deliveryDate.time.minutes}
					</p>
				{/if}

				<span class="material-symbols-outlined icon"> expand_more </span>

				{#if listOpen}
					<div class="absolute">
						<div class="list">
							<button
								on:click={() => {
									console.log('test');
									deliveryType = 'now';
								}}
							>
								<div>
									<svg
										width="20px"
										height="20px"
										fill="none"
										viewBox="0 0 24 24"
										xmlns="http://www.w3.org/2000/svg"
										aria-hidden="true"
										focusable="false"
									>
										<path
											d="M12 2.83398C6.91671 2.83398 2.83337 6.91732 2.83337 12.0007C2.83337 17.084 6.91671 21.1673 12 21.1673C17.0834 21.1673 21.1667 17.084 21.1667 12.0007C21.1667 6.91732 17.0834 2.83398 12 2.83398ZM17 13.6673H10.3334V5.33398H12.8334V11.1673H17V13.6673Z"
											fill="currentColor"
										/>
									</svg>
								</div>
								<p>Dostarcz teraz</p>
							</button>
							<button
								on:click={() => {
									dataForm.set(true);
									deliveryType = 'later';
								}}
							>
								<div>
									<svg
										width="20px"
										height="20px"
										fill="none"
										viewBox="0 0 24 24"
										xmlns="http://www.w3.org/2000/svg"
										aria-hidden="true"
										focusable="false"
									>
										<path
											fill-rule="evenodd"
											clip-rule="evenodd"
											d="M21.1666 8.66732V5.33398H18.6666V2.83398H16.1666V5.33398H7.83325V2.83398H5.33325V5.33398H2.83325V8.66732H21.1666ZM21.1666 21.1673H2.83325V10.334H21.1666V21.1673ZM8.66658 13.6673H6.16658V16.1673H8.66658V13.6673Z"
											fill="currentColor"
										/>
									</svg>
								</div>
								<p>Zaplanuj na później</p>
							</button>
						</div>
					</div>
				{/if}
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

				position: relative;

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

				.absolute {
					position: absolute;
					bottom: 0;
					left: 0;

					width: 100%;

					.list {
						position: absolute;

						min-height: 100%;

						display: flex;
						flex-direction: column;

						box-shadow: rgba(0, 0, 0, 0.1) 0px 0px 10px;
						background: #fff;

						z-index: 2;

						padding: 8px 0px 16px;

						button {
							/* width: 100%; */

							display: flex;
							align-items: center;
							gap: 8px;

							padding: 8px 16px;

							p {
								inline-size: max-content;
							}

							&:hover {
								background-color: rgb(246, 246, 246);
							}

							div {
								width: 32px;
								height: 32px;

								display: flex;
								justify-content: center;
								align-items: center;

								border-radius: 100%;
								background-color: rgb(246, 246, 246);
							}
						}
					}
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
