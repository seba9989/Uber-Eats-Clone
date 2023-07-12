<script lang="ts">
	import { dataForm } from '$lib/ts/Stores';
</script>

<svelte:head>
	<style>
		body {
			overflow: hidden;
		}
	</style>
</svelte:head>

{#if $dataForm}
	<main>
		<div class="relative">
			<div class="absolute">
				<div class="container">
					<div class="back">
						<button on:click={() => dataForm.set(false)}>
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
									d="m19.5831 6.24931-1.8333-1.83329-5.75 5.83328-5.75-5.83328-1.8333 1.83329 5.8333 5.74999-5.8333 5.75 1.8333 1.8333 5.75-5.8333 5.75 5.8333 1.8333-1.8333-5.8333-5.75z"
									fill="#000000"
								/>
							</svg>
						</button>
					</div>

					<div class="form">
						<h2>Wybierz godzinę</h2>

						<select name="" id="">
							<option value="">data</option>
						</select>

						<select name="" id="">
							<option value="">godzina</option>
						</select>

						<button class="black" on:click={() => dataForm.set(false)}>Zaplanuj</button>
						<button class="white" on:click={() => dataForm.set(false)}>Dostarcz teraz</button>
					</div>
				</div>
			</div>
		</div>
	</main>
{/if}

<style lang="scss">
	main {
		position: sticky;
		top: 0;
		z-index: 3;

		.relative {
			position: relative;

			.absolute {
				position: absolute;

				width: 100vw;
				height: 100vh;

				display: flex;
				flex-direction: column;
				align-items: center;

				background: rgba(38, 38, 38, 0.8);

				.container {
					width: 458px;

					margin-top: 80px;
					background-color: #fff;

					.back {
						width: 100%;
						height: 48px;
						padding: 24px 24px 0 24px;
					}

					.form {
						display: flex;
						flex-direction: column;
						padding: 24px;
						gap: 12px;

						h2 {
							font-size: 32px;
							font-weight: 700;

							margin-bottom: 12px;
						}

						select {
							background-color: rgb(238, 238, 238);
							border: none;
							padding: 12px 32px 12px 16px;
							outline: none;

							box-shadow: rgb(238, 238, 238) 0px -1px 0px inset;
							border: medium none;
							font-weight: normal;
							font-size: 16px;
							cursor: pointer;
						}

						button {
							font-size: 18px;

							padding: 12px 16px;

							border-radius: 8px;

							&.black {
								background: #000;
								color: #fff;

								&:hover {
									background: rgb(51, 51, 51);
								}
							}

							&.white {
								background: rgb(238, 238, 238);
								color: #000;

								&:hover {
									background: rgb(204, 204, 204);
								}
							}
						}
					}
				}
			}
		}
	}
</style>
