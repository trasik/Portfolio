<script lang="ts">
	import { setMode, resetMode, setTheme, theme } from 'mode-watcher';

	import BackgroundArcade from '$lib/assets/unsplash-arcade-bg.jpg';
	import BackgroundLava from '$lib/assets/unsplash-lava-bg.jpg';
	import BackgroundNYC from '$lib/assets/unsplash-nyc-bg.jpg';
	import IconSettings from '~icons/ic/round-settings';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu';
	import { Button } from '$lib/components/ui/button';
	import Background from './Background.svelte';

	let backgroundImage: string = BackgroundArcade;
</script>

<DropdownMenu.Root>
	<DropdownMenu.Trigger asChild let:builder>
		<Button variant="ghost" size="icon" builders={[builder]} class="rounded-full">
			<IconSettings class="text-[clamp(1rem,2vw,1.5rem)]" />
		</Button>
	</DropdownMenu.Trigger>
	<DropdownMenu.Content>
		<DropdownMenu.Label>Settings</DropdownMenu.Label>
		<DropdownMenu.Separator />
		<DropdownMenu.Sub>
			<DropdownMenu.SubTrigger>Mode</DropdownMenu.SubTrigger>
			<DropdownMenu.SubContent>
				<DropdownMenu.Item on:click={() => setMode('light')}>Light</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => setMode('dark')}>Dark</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => resetMode()}>System</DropdownMenu.Item>
			</DropdownMenu.SubContent>
		</DropdownMenu.Sub>
		<DropdownMenu.Sub>
			<DropdownMenu.SubTrigger>Themes</DropdownMenu.SubTrigger>
			<DropdownMenu.SubContent>
				<DropdownMenu.Item on:click={() => setTheme('winter')}>Winter</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => setTheme('cmyk')}>CMYK</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => setTheme('cupcake')}>Cupcake</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => setTheme('night')}>Night</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => setTheme('dracula')}>Dracula</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => setTheme('sunset')}>Sunset</DropdownMenu.Item>
			</DropdownMenu.SubContent>
		</DropdownMenu.Sub>
		<DropdownMenu.Sub>
			<DropdownMenu.SubTrigger>Backgrounds</DropdownMenu.SubTrigger>
			<DropdownMenu.SubContent>
				<DropdownMenu.Item on:click={() => (backgroundImage = BackgroundArcade)}>
					Arcade
				</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => (backgroundImage = BackgroundLava)}>
					Lava
				</DropdownMenu.Item>
				<DropdownMenu.Item on:click={() => (backgroundImage = BackgroundNYC)}>
					NYC Skyline
				</DropdownMenu.Item>
			</DropdownMenu.SubContent>
		</DropdownMenu.Sub>
	</DropdownMenu.Content>
</DropdownMenu.Root>

<Background {backgroundImage} />
