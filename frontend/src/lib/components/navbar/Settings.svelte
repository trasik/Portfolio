<script lang="ts">
	import { setMode, resetMode, setTheme, theme } from 'mode-watcher';

	import IconSettings from '~icons/ic/round-settings';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu';
	import { Button } from '$lib/components/ui/button';
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
				<DropdownMenu.Item>TODO</DropdownMenu.Item>
				<DropdownMenu.Item>TODO</DropdownMenu.Item>
				<DropdownMenu.Item>TODO</DropdownMenu.Item>
			</DropdownMenu.SubContent>
		</DropdownMenu.Sub>
	</DropdownMenu.Content>
</DropdownMenu.Root>
