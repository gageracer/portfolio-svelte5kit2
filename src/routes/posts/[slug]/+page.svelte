<script lang="ts">
	import type { Component } from 'svelte';
	import type { PageProps } from './$types';
	import Nav from '$lib/components/Nav.svelte';

	let { data }: PageProps = $props();
	const MDContent = data.content as Component;
</script>

<svelte:head>
	<title>{data.title}</title>
</svelte:head>
<MDContent />
<Nav />
