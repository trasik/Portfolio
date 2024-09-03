<script lang="ts">
	import Resume from '$lib/assets/TorendraRasikResume.pdf';

	import NavLink from './NavLink.svelte';
	import * as Avatar from '$lib/components/ui/avatar';
	import Settings from './Settings.svelte';
	import Clock from './Clock.svelte';
</script>

<header
	class="flex items-center justify-between px-[clamp(0.5rem,3vw,3.5rem)] py-[clamp(1rem,2vw,2rem)]"
>
	<nav class="flex gap-[clamp(0.75rem,2.5vw,2.5rem)]">
		<NavLink href="/" displayName="Home" />
		<NavLink href="/projects" displayName="Projects" />
	</nav>
	<div class="flex items-center gap-4 pb-1">
		<Settings />
		<div
			class="relative after:absolute after:bottom-0 after:right-0 after:h-[clamp(0.5rem,0.75vw,0.7rem)] after:w-[clamp(0.5rem,0.75vw,0.7rem)] after:rounded-full after:border-[1px] after:border-black after:bg-green-500 after:content-['']"
		>
			<a href={Resume} target="_blank">
				<Avatar.Root class="h-[clamp(1.5rem,2vw,2.5rem)] w-[clamp(1.5rem,2vw,2.5rem)]">
					<Avatar.Image src="https://github.com/shadcn.png" alt="@avatar" class="object-cover" />
					<Avatar.Fallback>TR</Avatar.Fallback>
				</Avatar.Root>
			</a>
		</div>
		<Clock />
	</div>
</header>
