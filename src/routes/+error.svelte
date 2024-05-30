<script>
	import Layout from "$lib/+layout.svelte";
	import Footer from "$lib/+footer.svelte";

	import { page } from "$app/stores";
</script>

<Layout>
	<div class="top-0 bottom-0 left-0 right-0 absolute">
		<div
			class="w-fit h-auto bg-[#39d7fe] mt-[75px] px-[20px] py-[5px] mx-auto rounded-lg"
		>
			<p class="font-bold text-[18px] text-[#000000]">Error: {$page.status}</p>
		</div>
		<p class="font-bold text-[18px] text-[#ffffff] mt-[30px]">
			{$page.error.message}
		</p>
		<Footer />
	</div>
</Layout>
