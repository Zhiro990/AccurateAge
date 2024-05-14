<script>
	let today = new Date().toISOString().split("T")[0];

	function Confirm() {
		let input = document.getElementById("input");

		location.href = "/?date=" + input.value;
	}
</script>

<p class="font-bold text-[18px] text-[#ffffff] mt-[150px]">
	Enter your birth date:
</p>

<input
	id="input"
	type="date"
	class="bg-[#303742] text-[16px] text-[#ffffff] px-[7.5px] py-[2.5px] mt-[25px] rounded-md outline-none"
	max={today}
/>

<br />

<button
	id="button"
	class="bg-[#39d7fe] text-[16px] text-[#000000] px-[5px] py-[2.5px] mt-[10px] rounded-lg"
	on:click={Confirm}
>
	Confirm
</button>
