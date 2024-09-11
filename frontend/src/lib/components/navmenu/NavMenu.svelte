<script lang="ts">
	import * as Card from '$lib/components/ui/card';
	import * as Carousel from '$lib/components/ui/carousel';

	export let basis: string;
	export let maxWidth: string;
	export let menuIcons;
</script>

<Carousel.Root class="w-full px-[clamp(1rem,4vw,6rem)] {maxWidth}">
	<Carousel.Content class="-ml-1 pb-8">
		{#each menuIcons as item}
			<Carousel.Item class="{basis} pl-1 transition-transform duration-300 hover:translate-y-8">
				<div class="group relative p-1">
					<Card.Root>
						<Card.Content class="flex aspect-square items-center justify-center p-6">
							<svelte:component this={item.icon} class="text-6xl text-primary sm:text-8xl " />
						</Card.Content>
					</Card.Root>
					<span
						class="absolute -top-8 left-0 right-0 mx-auto w-fit text-2xl opacity-0 transition-opacity duration-300 group-hover:opacity-100"
					>
						{item.header}
					</span>
				</div>
			</Carousel.Item>
		{/each}
	</Carousel.Content>
</Carousel.Root>
