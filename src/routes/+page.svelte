<script lang="ts">
	import RatingCard from '$lib/components/RatingCard.svelte';
	import ThanksCard from '$lib/components/ThanksCard.svelte';

	let isSubmitted: boolean = $state(false);
	let selectedRating: number = $state(0);
</script>

<div class="flex h-screen items-center justify-center">
	{#if !isSubmitted}
		<RatingCard bind:isSubmitted bind:selectedRating />
	{:else}
		<ThanksCard bind:selectedRating />
	{/if}
</div>
