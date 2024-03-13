<script>
	import Layout from "$lib/+layout.svelte";
	import Footer from "$lib/+footer.svelte"

	import { page } from "$app/stores";
</script>

<Layout>
	<div class="w-full h-auto mt-[75px]">
		<div
			class="w-fit h-auto bg-[#39d7fe] px-[20px] py-[5px] mx-auto rounded-lg"
		>
			<p class="font-bold text-[18px] text-[#000000]">Error: {$page.status}</p>
		</div>
		<p class="font-bold text-[18px] text-[#ffffff] mt-[30px]">
			{$page.error.message}
		</p>
	</div>

	<Footer />
</Layout>
