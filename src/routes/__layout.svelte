<script>
	import '../app.css';
	import Navbar from "$lib/components/navbar.svelte";
</script>
<div class="nav">
	<Navbar />
</div>
<slot />

<style>
	@media screen and (max-width:640px) {
		.nav {
			display: none;
		}
	}
</style>