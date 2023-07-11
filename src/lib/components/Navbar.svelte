<script lang="ts">
	let y: number;

	$: console.log(y);
</script>

<header class:white={y > 0}>
	<div class="left-side">
		<button class="hamburger-menu">
			<svg aria-hidden="true" focusable="false" viewBox="0 0 20 20" class="svg">
				<path
					d="M19.167 3.333H.833v2.5h18.334v-2.5zm0 5.834H.833v2.5h18.334v-2.5zM.833 15h18.334v2.5H.833V15z"
				/>
			</svg>
		</button>
		<img src="/UberLogo.svg" alt="Uber Eats" />
	</div>

	<nav class="right-side">
		<a href="/logIn" class="login">
			<span class="material-symbols-outlined"> person </span>
			Zaloguj się
		</a>
		<a href="/singIn" class="singin"> Zarejestruj się</a>
	</nav>
</header>

<svelte:window bind:scrollY={y} />

<style lang="scss">
	header {
		position: sticky;
		top: 0;

		width: 100%;
		height: 96px;

		display: flex;
		justify-content: space-between;
		align-items: center;

		padding: 0 40px;

		background: transparent;

		transition: background 500ms;

		&.white {
			background: #fff;
		}

		.left-side {
			display: flex;
			align-items: center;
			gap: 32px;

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
		}

		.right-side {
			display: flex;
			gap: 16px;

			font-weight: 500;

			a {
				min-height: 48px;

				padding: 12px 16px;

				border-radius: 500px;

				box-shadow: rgba(0, 0, 0, 0.1) 0px 0px 8px, rgba(0, 0, 0, 0.04) 0px 4px 4px;
			}

			.login {
				display: flex;

				gap: 4px;

				background: #fff;
			}

			.singin {
				background: #000;
				color: #fff;
			}
		}
	}
</style>
