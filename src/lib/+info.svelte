<script>
	export let birthday;

	function Change() {
		setInterval(() => {
			let info = document.getElementById("info");

			let age = (Date.now() - Date.parse(birthday)) / 31536000000;

			info.innerHTML = age.toFixed(10) + " years";
		}, 1);
	}
</script>

<div use:Change class="w-full h-auto absolute p-[20px] top-[100px]">
	<h1 class="text-[#ffffff] text-[30px] font-bold">Age</h1>
	<div class="w-fit h-auto bg-[#39d7fe] px-2 py-1 mt-2 mx-auto rounded-lg">
		<p id="info" class="font-[monospace] text-[#000000] text-[20px] break-all">
			???
		</p>
	</div>
</div>
