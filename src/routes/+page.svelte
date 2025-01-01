<script>
	import Layout from "$lib/+layout.svelte";

	let today = new Date().toISOString().split("T")[0];

	let date = "";
</script>

<Layout>
	<p id="name" class="font-bold text-[24px] text-[#39d7fe]">AccurateAge</p>

	<div
		id="container"
		class="h-auto w-fit bg-[#303742] px-[30px] py-[20px] mt-[60px] mx-auto rounded-md"
	>
		<p id="instruction" class="font-bold text-[17px] text-white">
			Enter your birth date:
		</p>

		<input
			id="input"
			type="date"
			class="h-auto w-full bg-[#1f232e] text-[16px] text-white text-center px-[7.5px] py-[2.5px] mt-[15px] rounded-md outline-none"
			max={today}
			bind:value={date}
			on:change={() => {
				let x = new Date(date);
				let now = new Date();

				let years = 0;
				let months = 0;
				let days = 0;

				let days_only = Math.floor(
					(Date.parse(now) - Date.parse(x)) / 86400000
				);

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
					x.getFullYear(),
					x.getMonth() + months,
					x.getDate()
				);
				
				days = Math.floor((Date.parse(now) - Date.parse(x)) / 86400000);

				document.querySelector("#years-months-days").textContent =
					`${years} year${years > 1 ? "s" : ""}, ${months} month${
						months > 1 ? "s" : ""
					}, ${days} day${days > 1 ? "s" : ""}`;

				document.querySelector("#days-only").textContent = `${days_only} day${
					days_only > 1 ? "s" : ""
				}`;
			}}
		/>

		<div id="results" class="h-auto w-full mt-[25px]">
			<div
				id="years-months-days-container"
				class="h-auto w-full bg-[#39d7fe] p-[7.5px] rounded-t-lg"
			>
				<p id="years-months-days" class="font-bold text-[17px] text-black">
					0 year, 0 month, 0 day
				</p>
			</div>
			<div
				id="days-only-container"
				class="h-auto w-full bg-[#1f232e] p-[7.5px] rounded-b-lg"
			>
				<p id="days-only" class="text-[17px] text-white">0 day</p>
			</div>
		</div>
	</div>
</Layout>
