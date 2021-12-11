<script>
	import '../app.css';
	import Navbar from "$lib/components/navbar.svelte";
	import Footer from "$lib/components/footer.svelte";
</script>
<div class="nav">
	<Navbar />
</div>
<slot />
<div class="foot">
	<Footer />
</div>

<style>
	@media screen and (max-width:767px) {
		.nav {
			display: none;
		}

		.foot {
			display: none;
		}
	}
</style>