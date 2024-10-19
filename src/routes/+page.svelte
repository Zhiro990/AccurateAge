<script>
	import Layout from "$lib/+layout.svelte";
	import Input from "$lib/+input.svelte";
	import Info from "$lib/+info.svelte";
	import Footer from "$lib/+footer.svelte";

	import { page } from "$app/stores";

	let date = $page.url.searchParams.get("date");
</script>

<Layout>
	<div class="top-0 bottom-0 left-0 right-0 absolute">
		<div
			class="w-fit h-auto bg-[#39d7fe] px-[20px] py-[5px] mt-[100px] mx-auto rounded-lg"
		>
			<p class="font-bold text-[21px] text-[#000000]">AccurateAge</p>
		</div>

		{#if !date}
			<Input />
		{:else}
			<Info {date} />
		{/if}

		<Footer />
	</div>
</Layout>
