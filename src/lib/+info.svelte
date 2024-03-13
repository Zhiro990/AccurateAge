<script>
	import Footer from "$lib/+footer.svelte";

	export let birthday;

	function Change() {
		setInterval(() => {
			let info = document.getElementById("info");

			let age = (Date.now() - Date.parse(birthday)) / 31556952000;

			info.innerHTML = age.toFixed(10) + " years";
		}, 1);
	}
</script>

<div use:Change class="w-full h-auto mt-[150px]">
	<p class="font-bold text-[18px] text-[#ffffff]">Your age is:</p>
	<div
		class="w-fit h-auto bg-[#39d7fe] px-[5px] py-[2.5px] mt-[25px] mx-auto rounded-lg"
	>
		<p id="info" class="font-mono text-[18px] text-[#000000]">???</p>
	</div>
</div>

<Footer />
