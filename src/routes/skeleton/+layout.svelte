<script>
	import '@skeletonlabs/skeleton/themes/theme-vintage.css';
	import '@skeletonlabs/skeleton/styles/all.css';
	import '../../app.postcss';
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
	import { onMount } from 'svelte';

	// with the below routine the FOUC is almost not present. Only font/text change slightly visible on "Welcome to Skeleton"
	let visible = false;
	onMount(() => {
		console.log('Layout onMount');
		setTimeout(() => {
			visible = true;
		}, 3000);
	});

	console.log('Layout main');
</script>

<!-- App Shell -->
{#if visible}
	<AppShell slotSidebarLeft="bg-surface-500/5 w-56 p-4">
		<svelte:fragment slot="header">
			<!-- App Bar -->
			<AppBar>
				<svelte:fragment slot="lead">
					<strong class="text-xl uppercase">Skeleton</strong>
				</svelte:fragment>
				<svelte:fragment slot="trail">
					<a
						class="btn btn-sm btn-ghost-surface"
						href="https://discord.gg/EXqV7W8MtY"
						target="_blank"
						rel="noreferrer">Discord</a
					>
					<a
						class="btn btn-sm btn-ghost-surface"
						href="https://twitter.com/SkeletonUI"
						target="_blank"
						rel="noreferrer">Twitter</a
					>
					<a
						class="btn btn-sm btn-ghost-surface"
						href="https://github.com/skeletonlabs/skeleton"
						target="_blank"
						rel="noreferrer">GitHub</a
					>
				</svelte:fragment>
			</AppBar>
		</svelte:fragment>
		<!-- Page Route Content -->
		<slot />
	</AppShell>
{/if}
