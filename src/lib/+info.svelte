<script>
	export let birthday;

	let length = 10;

	function Change() {
		setInterval(() => {
			let info = document.getElementById("info");

			let age = (Date.now() - Date.parse(birthday)) / 31536000000;

			info.innerHTML =
				age.toFixed(length) + (length == 10 ? " " : "<br>") + "years";
		}, 1);
	}

	function ExpandCollapse() {
		let arrow = document.getElementById("arrow");
		arrow.classList.toggle("rotate-0");

		length = length == 10 ? 49 : 10;
	}
</script>

<div use:Change class="w-full h-auto absolute p-[20px] top-[100px]">
	<h1 class="text-[#ffffff] text-[30px] font-bold">Age</h1>
	<div class="w-fit h-auto bg-[#39d7fe] px-2 py-1 mt-2 mx-auto rounded-lg">
		<p id="info" class="font-[monospace] text-[#000000] text-[20px] break-all">
			???
		</p>
	</div>
	<button class="mt-2 mx-auto" on:click={ExpandCollapse}>
		<img
			id="arrow"
			src="./pictures/arrow.svg"
			class="w-[30px] rotate-180"
			alt="arrow"
		/>
	</button>
</div>
