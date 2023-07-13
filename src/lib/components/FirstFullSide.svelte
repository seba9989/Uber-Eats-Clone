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

	let innerWidth: number;

	let mobileVersion: boolean;

	$: if (innerWidth != undefined) {
		mobileVersion = innerWidth < 500;
	}
</script>

<svelte:window bind:innerWidth />

<main>
	<div>
		{#if !mobileVersion}
			<h1>Zamów jedzenie pod drzwi</h1>
		{:else}
			<h2>Zamów jedzenie pod drzwi</h2>
		{/if}
		<div class="search-bar">
			<div class="text-input">
				<svg
					width="24px"
					height="24px"
					fill="none"
					viewBox="0 0 24 24"
					xmlns="http://www.w3.org/2000/svg"
					aria-hidden="true"
					focusable="false"
				>
					<path
						d="M17.5834 5.16602C14.5001 2.08268 9.50008 2.08268 6.41675 5.16602C3.33341 8.24935 3.33341 13.3327 6.41675 16.416L12.0001 21.9993L17.5834 16.3327C20.6667 13.3327 20.6667 8.24935 17.5834 5.16602ZM12.0001 12.416C11.0834 12.416 10.3334 11.666 10.3334 10.7493C10.3334 9.83268 11.0834 9.08268 12.0001 9.08268C12.9167 9.08268 13.6667 9.83268 13.6667 10.7493C13.6667 11.666 12.9167 12.416 12.0001 12.416Z"
						fill="currentColor"
					/>
				</svg>
				<input type="text" placeholder="Wpisz adres dostawy" />
			</div>

			<button class="select-menu" on:click={() => (listOpen = !listOpen)}>
				{#if deliveryType === 'now'}
					<div class="icon">
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
				{:else if deliveryDate}
					<div class="icon">
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
					<p>
						{deliveryDate.data.day}-{deliveryDate.data.month}-{deliveryDate.data.year},
						{deliveryDate.time.hour}:{deliveryDate.time.minutes}
					</p>
				{/if}

				<svg
					width="24px"
					height="24px"
					fill="none"
					viewBox="0 0 24 24"
					xmlns="http://www.w3.org/2000/svg"
					aria-hidden="true"
					focusable="false"
					style="position: absolute; right: 4px; padding: 12px;"
					class="icon"
				>
					<path
						d="M17 11.7494V14.916L12 11.0827L7 14.916V11.7494L12 7.91602L17 11.7494Z"
						fill="#000000"
						transform="rotate(180, 12, 12)"
					/>
				</svg>

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

		@media (max-width: 500px) {
			justify-content: start;

			background-image: url('https://d3i4yxtzktqr9n.cloudfront.net/web-eats-v2/3dec1d1b7e1b5874.png');

			padding: 0 16px;

			padding-top: 72px;

			margin-bottom: 48px;
		}

		h1 {
			margin-bottom: 40px;

			font-size: 52px;
			font-weight: 700;
			line-height: 64px;
		}

		h2 {
			font-size: 36px;
			font-weight: 700;
		}

		.search-bar {
			display: flex;
			gap: 8px;

			@media (max-width: 500px) {
				flex-direction: column;
			}

			* {
				font-size: 1rem;
			}

			.text-input {
				width: 540px;
				height: 56px;

				@media (max-width: 500px) {
					width: 100%;
				}

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
					/* aspect-ratio: 1/1; */
					height: 48px;
					width: 48px;

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

			font-size: 14px;
		}
	}
</style>
