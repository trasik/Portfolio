<script lang="ts">
	import { page } from '$app/stores';

	export let href: string;
	export let displayName: string;
</script>

<a
	{href}
	class="{$page.url.pathname === href
		? 'font-semibold'
		: ''} text-[clamp(1rem,2vw,1.5rem)] after:block after:h-1 after:origin-left after:scale-x-0 after:rounded-full after:bg-sky-500 after:transition-transform after:duration-300 after:content-[''] after:hover:scale-x-100"
>
	{displayName}
</a>
