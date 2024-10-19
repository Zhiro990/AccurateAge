<script>
	export let date;

	function Change() {
		let info = document.getElementById("info");
		let addition = document.getElementById("addition");

		let x = new Date(date + "T00:00:00.000+07:00");
		let now = new Date();

		if (x == "Invalid Date" || Date.parse(x) > Date.parse(now)) {
			info.innerHTML = "Error!";
			addition.innerHTML = "Invalid Date!";

			return;
		}

		let years = 0;
		let months = 0;
		let days = 0;

		let days_only = Math.floor((Date.parse(now) - Date.parse(x)) / 86400000);

		years +=
			now.getFullYear() -
			x.getFullYear() -
			(x.getMonth() < now.getMonth() ||
			(x.getMonth() == now.getMonth() && x.getDate() <= now.getDate())
				? 0
				: 1);

		x = new Date(x.getFullYear() + years, x.getMonth(), x.getDate());

		months =
			x.getFullYear() < now.getFullYear()
				? 11 -
					x.getMonth() +
					now.getMonth() +
					(x.getDate() <= now.getDate() ? 1 : 0)
				: now.getMonth() -
					x.getMonth() -
					(x.getDate() <= now.getDate() ? 0 : 1);

		x = new Date(
			now.getFullYear(),
			((x.getMonth() + 1 + months) % 12) - 1,
			x.getDate()
		);

		days = Math.floor((Date.parse(now) - Date.parse(x)) / 86400000);

		info.innerHTML = `${years} year${years > 1 ? "s" : ""}, ${months} month${
			months > 1 ? "s" : ""
		}, ${days} day${days > 1 ? "s" : ""}`;

		addition.innerHTML = `${days_only} day${days_only > 1 ? "s" : ""}`;
	}
</script>

<p class="font-bold text-[17px] text-[#ffffff] mt-[50px]">Your age is:</p>

<div class="w-fit h-auto mt-[20px] mx-auto">
	<div class="w-full h-auto bg-[#39d7fe] px-[20px] py-[10px] rounded-t-lg">
		<p use:Change id="info" class="font-bold text-[17px] text-[#000000]">...</p>
	</div>

	<div class="w-full h-auto bg-[#303742] px-[20px] py-[10px] rounded-b-lg">
		<p id="addition" class="text-[17px] text-[#ffffff]">...</p>
	</div>
</div>
