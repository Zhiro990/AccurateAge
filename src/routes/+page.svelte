<script>
	import Layout from "$lib/+layout.svelte";
	import Input from "$lib/+input.svelte";
	import Info from "$lib/+info.svelte";
	import Footer from "$lib/+footer.svelte";

	import { page } from "$app/stores";

	let birthday = $page.url.searchParams.get("date");
</script>

<Layout>
	{#if !birthday}
		<Input />
	{:else}
		<Info {birthday} />
	{/if}
	
	<Footer />
</Layout>
