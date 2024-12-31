<script>
	import Layout from "$lib/+layout.svelte";

	import { page } from "$app/stores";
</script>

<Layout>
	<div
		id="error-code-container"
		class="h-auto w-fit px-[20px] py-[5px] mt-[50px] mx-auto border-[1px] border-[#39d7fe] rounded-lg"
	>
		<p id="error-code" class="font-bold text-[20px] text-white">
			Error: {$page.status}
		</p>
	</div>
	<p id="error-message" class="font-bold text-[20px] text-white mt-[30px]">
		{$page.error.message}
	</p>
</Layout>
