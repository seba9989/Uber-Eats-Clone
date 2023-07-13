<script lang="ts">
	import { hamburgerOpen } from '$lib/ts/Stores';

	let y: number;

	let innerWidth: number;

	let mobileVersion: boolean;

	$: if (innerWidth != undefined) {
		mobileVersion = innerWidth < 500;
		// console.log(mobileVersion);
	}

	// $: console.log(innerWidth);
</script>

<svelte:window bind:scrollY={y} bind:innerWidth />

<div class="h0">
	<header class:white={y > 0}>
		<div class="left-side">
			<button class="hamburger-menu" on:click={() => hamburgerOpen.set(true)}>
				<svg aria-hidden="true" focusable="false" viewBox="0 0 20 20" class="svg">
					<path
						d="M19.167 3.333H.833v2.5h18.334v-2.5zm0 5.834H.833v2.5h18.334v-2.5zM.833 15h18.334v2.5H.833V15z"
					/>
				</svg>
			</button>
			<img src="/UberLogo.svg" alt="Uber Eats" />

			{#if !mobileVersion}
				<div class="text-input" class:show={y > 450}>
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
			{/if}
		</div>

		<nav class="right-side">
			<a href="/logIn" class="login">
				<svg aria-hidden="true" focusable="false" viewBox="0 0 26 26">
					<path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M18.958 7.042a5.958 5.958 0 11-11.916 0 5.958 5.958 0 0111.916 0zM3.25 21.667c0-3.575 2.925-6.5 6.5-6.5h6.5c3.575 0 6.5 2.925 6.5 6.5v3.25H3.25v-3.25z"
					/>
				</svg>
				{#if !mobileVersion}
					Zaloguj się
				{/if}
			</a>
			<a href="/singIn" class="singin"> Zarejestruj się</a>
		</nav>
	</header>
</div>

{#if mobileVersion && y > 450}
	<div class="sticky">
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
	</div>
{/if}

<style lang="scss">
	.h0 {
		position: sticky;
		top: 0;

		height: 0;

		@media (max-width: 500px) {
			position: absolute;
			height: fit-content;
		}
	}

	header {
		width: 100%;
		height: 96px;

		@media (max-width: 500px) {
			height: 72px;
		}

		display: flex;
		justify-content: space-between;
		align-items: center;

		@media (max-width: 500px) {
			& {
				padding: 0 16px;
			}
		}
		padding: 0 40px;

		box-shadow: none;

		background: transparent;

		transition: all 200ms;

		@media (min-width: 500px) {
			&.white {
				background: #fff;
				box-shadow: rgb(226, 226, 226) 0px -2px 0px inset;
			}
		}

		.left-side {
			display: flex;
			align-items: center;
			gap: 32px;

			@media (max-width: 500px) {
				& {
					gap: 24px;
				}
			}

			.hamburger-menu {
				aspect-ratio: 1 / 1;
				height: 24px;
				display: flex;
				justify-content: center;
				align-items: center;

				.svg {
					width: 20px;
				}
			}

			@media (max-width: 500px) {
				img {
					height: 20px;
				}
			}
		}

		.text-input {
			height: 56px;
			width: 0;

			display: flex;
			align-items: center;
			gap: 16px;

			padding: 8px 0px;

			border: medium none;

			margin-left: 128px;

			background: #ddd;

			line-height: 24px;
			font-size: 16px;

			box-shadow: rgb(238, 238, 238) 0px -1px 0px inset;

			transition: all 500ms;

			overflow: hidden;

			input {
				height: 100%;
				width: 100%;

				border: none;
				font-weight: normal;

				background: #ddd;
				padding: 0;

				&:focus {
					outline: 0;
				}
			}

			&.show {
				width: 722px;

				padding: 8px 16px;
			}
		}

		.right-side {
			display: flex;
			gap: 16px;

			font-weight: 500;

			a {
				display: flex;
				align-items: center;

				padding: 12px 16px;

				border-radius: 500px;

				box-shadow: rgba(0, 0, 0, 0.1) 0px 0px 8px, rgba(0, 0, 0, 0.04) 0px 4px 4px;

				@media (max-width: 500px) {
					& {
						padding: 12px;
						white-space: nowrap;
						font-size: 14px;
						height: 36px;
					}
				}
			}

			.login {
				gap: 4px;

				background: #fff;

				&:hover {
					background: rgb(204, 204, 204);
				}

				svg {
					height: 20px;
					width: 20px;

					@media (max-width: 500px) {
						height: 16px;
						width: 16px;
					}
				}
			}

			.singin {
				background: #000;
				color: #fff;

				&:hover {
					background: rgb(51, 51, 51);
				}
			}
		}
	}

	.sticky {
		position: sticky;
		top: 0;

		height: 0;

		z-index: 2;
		.text-input {
			height: 72px;

			display: flex;
			align-items: center;
			gap: 16px;

			padding: 8px 16px;

			background: #ddd;

			line-height: 24px;
			font-size: 16px;

			overflow: hidden;

			border: #fff solid;
			border-width: 8px 16px;

			box-shadow: rgb(226, 226, 226) 0px 0px 10px;

			input {
				height: 100%;
				width: 100%;

				border: none;
				font-weight: normal;

				background: #ddd;
				padding: 0;

				&:focus {
					outline: 0;
				}
			}
		}
	}
</style>
