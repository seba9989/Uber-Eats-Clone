<script lang="ts">
	import HamburgerMenu from '$lib/components/HamburgerMenu/HamburgerMenu.svelte';
	import Navbar from '$lib/components/Navbar.svelte';
	import '../lib/style/app.scss';

	import { HamburgerOpen } from '$lib/ts/HamburgerStore';
</script>

<HamburgerMenu />

<div class:hidden={$HamburgerOpen}>
	<Navbar />
	<slot />
</div>

<style lang="scss">
	div {
		min-height: 100vh;

		margin: 0;

		display: flex;
		flex-direction: column;

		&.hidden {
			z-index: -1;
		}
	}
</style>
