<script>
	import ThemeSwitcher from '$lib/themes/themeSwitcher.svelte';
</script>

<div class="navbar bg-base-100 sticky shadow-sm">
	<div class="flex-1">
		<a class="btn btn-ghost text-xl">postFetcher</a>
	</div>
	<div class="flex-none">
		<ThemeSwitcher />
	</div>
</div>
