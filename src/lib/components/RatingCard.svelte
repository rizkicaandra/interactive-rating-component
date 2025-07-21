<script lang="ts">
	const totalRating = Array.from({ length: 5 }, (_, i) => i + 1);
	let {
		isSubmitted = $bindable(false),
		selectedRating = $bindable(0)
	}: { isSubmitted: boolean; selectedRating: number } = $props();

	function handleRating(rating: number) {
		selectedRating = rating;
	}

	function submitRating() {
		isSubmitted = true;
	}
</script>

<div
	class="bg-radial-custom flex max-w-max-card-container-mobile flex-col gap-6 rounded-3.75 px-6 py-7.12 text-preset-5-bold md:max-w-max-card-container-tablet md:gap-8 md:rounded-7.5 md:px-7.62 md:py-8.62"
>
	<!-- star icon -->
	<div class="flex h-10 w-10 items-center justify-center rounded-full bg-grey-900 md:h-12 md:w-12">
		<svg width="17" height="16" xmlns="http://www.w3.org/2000/svg"
			><path
				d="m9.067.43 1.99 4.031c.112.228.33.386.58.422l4.45.647a.772.772 0 0 1 .427 1.316l-3.22 3.138a.773.773 0 0 0-.222.683l.76 4.431a.772.772 0 0 1-1.12.813l-3.98-2.092a.773.773 0 0 0-.718 0l-3.98 2.092a.772.772 0 0 1-1.119-.813l.76-4.431a.77.77 0 0 0-.222-.683L.233 6.846A.772.772 0 0 1 .661 5.53l4.449-.647a.772.772 0 0 0 .58-.422L7.68.43a.774.774 0 0 1 1.387 0Z"
				fill="#FC7614"
			/></svg
		>
	</div>

	<!-- select rating -->
	<div class="flex flex-col gap-4">
		<span class="text-preset-2 text-white md:text-preset-1"> How did we do? </span>

		<p class="text-preset-5-regular text-grey-500 md:text-preset-4-regular">
			Please let us know how we did with your support request. All feedback is appreciated to help
			us improve our offering!
		</p>

		<div class="flex items-center justify-between text-grey-500">
			{#each totalRating as rating}
				<button
					type="button"
					aria-label="rating-{rating}"
					onclick={() => handleRating(rating)}
					class="flex h-10.5 w-10.5 cursor-pointer items-center justify-center rounded-full {selectedRating ===
					rating
						? 'bg-white text-grey-950'
						: 'bg-grey-900 text-grey-500'} transition duration-200 ease-in-out hover:bg-orange-500 hover:text-grey-900 active:bg-white active:text-grey-950 md:h-12.75 md:w-12.75 md:text-preset-3"
					>{rating}</button
				>
			{/each}
		</div>
	</div>

	<button
		type="submit"
		aria-label="submit-rating"
		onclick={submitRating}
		disabled={!selectedRating}
		class="w-full cursor-pointer rounded-5.6 bg-orange-500 py-3.5 text-center text-grey-950 uppercase transition duration-200 ease-in-out hover:bg-white hover:text-grey-950 active:bg-white active:text-grey-950 disabled:cursor-not-allowed hover:disabled:bg-orange-500 md:text-preset-5-semi-bold"
		>submit</button
	>
</div>
