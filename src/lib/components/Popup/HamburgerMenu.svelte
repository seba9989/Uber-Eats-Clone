<script lang="ts">
	import { hamburgerOpen } from '$lib/ts/Stores';
	import { fade, fly } from 'svelte/transition';
</script>

{#if $hamburgerOpen}
	<main>
		<div class="relative">
			<div class="absolute" in:fade={{ duration: 200 }} out:fade={{ duration: 200 }}>
				<div
					class="menu"
					in:fly={{ x: '-125%', duration: 200 }}
					out:fly={{ x: '-125%', duration: 200 }}
				>
					<div>
						<a href="/" class="singIn button">Zarejestruj się</a>
						<a href="/" class="login button">Zaloguj się</a>

						<ul>
							<li><a href="/"> Utwórz konto firmowe </a></li>
							<li><a href="/">Dodaj swoją restaurację</a></li>
							<li><a href="/">Zarejestruj się, aby realizować dostawy</a></li>
						</ul>
					</div>

					<div class="bottom">
						<div class="top">
							<img
								src="https://d3i4yxtzktqr9n.cloudfront.net/web-eats-v2/31ee382bd0e6ed84.svg"
								alt=""
								class="icon"
							/>

							<p>W aplikacji wybór jest jeszcze większy.</p>
						</div>

						<div class="links">
							<a href="/">
								<svg aria-hidden="true" focusable="false" viewBox="0 0 24 24" style="width: 24px;">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M14.268 4.231c.649-.838 1.14-2.022.963-3.231-1.061.074-2.301.752-3.025 1.637-.66.802-1.201 1.994-.99 3.152 1.16.036 2.357-.66 3.052-1.558zM20 15.602c-.464 1.035-.688 1.497-1.285 2.413-.834 1.28-2.01 2.872-3.47 2.884-1.294.014-1.628-.849-3.385-.838-1.758.01-2.124.854-3.421.841-1.458-.013-2.572-1.45-3.406-2.729-2.334-3.574-2.58-7.769-1.14-10C4.916 6.587 6.53 5.66 8.048 5.66c1.543 0 2.515.852 3.793.852 1.24 0 1.995-.854 3.78-.854 1.352 0 2.784.74 3.803 2.018-3.34 1.842-2.8 6.642.576 7.925z"
									/>
								</svg>
								iPhone
							</a>
							<a href="/"><span class="material-symbols-outlined"> android </span> Android</a>
						</div>
						<div />
					</div>
				</div>

				<button class="back" on:click={() => hamburgerOpen.set(false)} />
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

				background: rgba(38, 38, 38, 0.8);

				.menu {
					width: 300px;

					background: #fff;

					display: flex;
					flex-direction: column;
					justify-content: space-between;

					padding: 24px;

					div {
						display: flex;
						flex-direction: column;

						.button {
							font-size: 18px;
							padding: 12px 16px;

							border-radius: 8px;

							display: flex;
							justify-content: center;
							align-items: center;

							&.singIn {
								background: #000;
								color: #fff;

								margin-bottom: 8px;
							}

							&.login {
								background: rgb(238, 238, 238);
							}
						}

						ul {
							list-style: none;
							padding: 0;
							font-size: 14px;

							margin-top: 24px;

							li {
								margin-bottom: 16px;
							}
						}

						&.bottom {
							.top {
								display: flex;
								flex-direction: row;
								gap: 16px;

								.icon {
									width: 56px;
								}
							}

							.links {
								flex-direction: row;
								gap: 8px;

								a {
									display: flex;
									justify-content: center;
									align-items: center;
									gap: 8px;

									padding: 12px;

									border-radius: 500px;

									background: rgb(238, 238, 238);
								}
							}
						}
					}
				}

				.back {
					width: calc(100vw - 300px);

					cursor: default;
				}
			}
		}
	}
</style>
