<script>
	import CommentIcon from './icons/commentIcon.svelte';
	import LikeIcon from './icons/likeIcon.svelte';

	const btnText = 'lookup';

	let data = null;
	let username = '';

	async function fetchPosts(user) {
		try {
			const response = await fetch(`https://pikidiary-api.vercel.app/?username=${user}`);

			data = await response.json();
		} catch (error) {
			console.error(error.message);
		}
	}
</script>

<div class="flex flex-col items-center justify-center gap-5">
	<input
		type="text"
		placeholder="Enter username here..."
		class="input input-primary"
		bind:value={username}
	/>
	<button class="btn btn-primary" onclick={() => fetchPosts(username)}>{btnText}</button>

	{#if data}
		{#each data.posts as post}
			<div class="bg-base-100 rounded-box w-full max-w-2xl p-5 shadow-xl">
				<div class="flex items-center gap-2">
					<div class="avatar">
						<div class="w-13 rounded-full shadow-xl">
							<img src={data.pfp} alt="pfp" />
						</div>
					</div>
					<div class="flex gap-3 items-center"><p class="text-left align-middle text-lg font-bold">{post.author}</p><p class="text-gray-400">{post.createdAt}</p></div>
				</div>
				<div class="text-left break-all">{post.content}</div>
				<div class="divider"></div>
				<div class="flex justify-between">
					<div id="likeCount" class="flex gap-1">
						<LikeIcon />
						<span class="align-middle">{post.likes}</span>
					</div>
					<div id="commentCount">
						<a href={post.url} class="flex gap-1">
							<CommentIcon />
							<span class="align-middle">{post.comments}</span>
						</a>
					</div>
				</div>
			</div>
		{/each}
	{/if}
</div>
