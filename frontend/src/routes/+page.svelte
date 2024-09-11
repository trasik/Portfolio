<script>
	import IconAbout from '~icons/hugeicons/alien-01';
	import IconWork from '~icons/hugeicons/work-history';
	import IconBlog from '~icons/hugeicons/pencil-edit-01';
	import IconContact from '~icons/hugeicons/contact-01';
	import NavMenu from '$lib/components/navmenu/NavMenu.svelte';

	const menuIcons = [
		{
			icon: IconAbout,
			header: 'About Me'
		},
		{
			icon: IconWork,
			header: 'Experience'
		},
		{
			icon: IconBlog,
			header: 'Blog'
		},
		{
			icon: IconContact,
			header: 'Contact Me'
		}
	];
</script>

<NavMenu basis="basis-1/3 sm:basis-1/4" maxWidth="max-w-5xl" {menuIcons} />
