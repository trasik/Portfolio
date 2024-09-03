<script lang="ts">
	import '../app.css';
	import { ModeWatcher } from 'mode-watcher';
	import NavBar from '$lib/components/navbar/NavBar.svelte';
</script>

<ModeWatcher />
<NavBar />
<slot></slot>
