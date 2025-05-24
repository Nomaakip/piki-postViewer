<script>
	let { username = $bindable('') } = $props();
</script>

<input type="text" placeholder="Enter username here..." class="input input-primary" />
<p>{username}</p>
