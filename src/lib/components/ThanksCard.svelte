<script lang="ts">
	let { selectedRating = $bindable(0) }: { selectedRating: number } = $props();
</script>

<div
	class="bg-radial-custom flex max-w-max-card-container-mobile flex-col items-center justify-center gap-6 rounded-3.75 px-6 py-9 md:max-w-max-card-container-tablet md:gap-8 md:px-8.62 md:py-11"
>
	<div>
		<img
			src="/illustration-thank-you.svg"
			alt="illustration-thank-you"
			class="h-24 w-36 md:h-27 md:w-40.5"
		/>
	</div>
	<div
		class="rounded-3.75 bg-grey-900 px-3 py-1.25 text-preset-5-regular text-orange-500 md:px-5 md:py-1 md:text-preset-4-regular"
	>
		<span class="text-center">You selected {selectedRating} out of 5</span>
	</div>
	<div class="flex flex-col items-center justify-center gap-4 text-center">
		<h1 class="text-preset-2 text-white md:text-preset-1">Thank You</h1>
		<p class="text-preset-5-regular text-grey-500 md:text-preset-4-regular">
			We appreciate you taking the time to give a rating. If you ever need more support, don’t
			hesitate to get in touch!
		</p>
	</div>
</div>
