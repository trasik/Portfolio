<script lang="ts">
	import { onMount } from 'svelte';

	let currentDate = new Date();

	$: currentTime = currentDate.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit' });

	onMount(() => {
		const interval = setInterval(() => {
			currentDate = new Date();
		}, 1000);

		return () => {
			clearInterval(interval);
		};
	});
</script>

<span class="ml-4 text-[clamp(1rem,2vw,1.5rem)]">{currentTime}</span>
