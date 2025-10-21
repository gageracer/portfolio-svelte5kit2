<script lang="ts">
	import { onNavigate } from '$app/navigation';
	import '../app.css';
	import { page } from '$app/state';

	let { children } = $props();
	let imgHover = $state(false);
	const home = $derived(page.url.pathname === '/');
	const name = 'John Can Aygin';

	const pictureAnimate = () => {
		const count = setInterval(() => {
			imgHover = true;
		}, 4000);

		return clearInterval(count);
	};
</script>

<div class="from-primary to-secondary text-text min-h-screen bg-gradient-to-br">
	<main class="container mx-auto px-4 py-8">
		<div class="container mx-auto max-w-2xl px-4 py-8">
			<header class="flex flex-col items-center">
				{#if home}
					<div class="mb-4">
						<img
							src={imgHover ? '/images/profile2.jpeg' : '/images/profile.jpeg'}
							alt={name}
							class="h-40 w-40 rounded-full shadow-lg transition-shadow duration-300"
							onmouseenter={() => pictureAnimate()}
							onmouseleave={() => (imgHover = false)}
						/>
					</div>
					<h1 class="text-4xl font-bold">{name}</h1>
				{:else}
					<div class="mb-4">
						<a href="/">
							<img src="/images/profile.jpeg" alt={name} class="h-24 w-24 rounded-full shadow-md" />
						</a>
					</div>
					<h2 class="text-2xl font-bold">
						<a href="/" class="text-text hover:no-underline">{name}</a>
					</h2>
				{/if}
			</header>
			{@render children()}
		</div>
	</main>
</div>
