<script>
	import Fetch from '$lib/fetch.svelte';
    import ThemeSwitcher from '$lib/themes/themeSwitcher.svelte';
    import Navbar from '$lib/nav/navbar.svelte';
	import Footer from '$lib/nav/footer.svelte';
</script>

<Navbar />

<div class="hero bg-base-200 min-h-screen">
	<div class="hero-content text-center flex-col">
		<h1 class="text-5xl font-bold">postFetcher</h1>
		<Fetch />
	</div>
</div>

<Footer />

