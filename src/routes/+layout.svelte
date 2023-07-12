<script lang="ts">
	import HamburgerMenu from '$lib/components/Popup/HamburgerMenu.svelte';
	import Navbar from '$lib/components/Navbar.svelte';
	import '../lib/style/app.scss';

	import { hamburgerOpen, dataForm } from '$lib/ts/Stores';
	import DataForm from '$lib/components/Popup/DataForm.svelte';

	let popup = false;

	$: if ($hamburgerOpen || $dataForm) {
		popup = true;
	} else if (!$hamburgerOpen && !$dataForm) {
		popup = false;
	}
</script>

<DataForm />
<HamburgerMenu />

<Navbar />
<slot />
