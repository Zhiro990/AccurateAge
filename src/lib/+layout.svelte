<script>
	import "../app.css";
	import Footer from "$lib/+footer.svelte";
</script>

<div id="page" class="top-0 bottom-0 left-0 right-0 absolute">
	<div id="main" class="h-screen w-full pt-[70px]">
		<slot />
	</div>

	<Footer />
</div>
