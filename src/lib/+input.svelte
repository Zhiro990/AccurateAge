<script>
	let today = new Date().toISOString().split("T")[0];

	function Confirm() {
		let input = document.getElementById("input");
		window.location.href = "/?date=" + input.value;
	}
</script>

<div class="w-full h-auto mt-[150px]">
	<h1 class="text-[#ffffff] text-[18px] font-bold">Enter your birthday:</h1>
	<input
		id="input"
		type="date"
		class="bg-[#303742] text-[#ffffff] px-2 py-1 mt-1 rounded-md outline-none"
		max={today}
	/>
	<br />
	<button
		id="button"
		class="bg-[#39d7fe] text-[#000000] px-2 py-1 mt-2 rounded-lg"
		on:click={Confirm}
	>
		Confirm
	</button>
</div>
