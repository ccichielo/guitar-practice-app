<script lang="ts">
	let notes: string[] = [
		"A",
		"A#",
		"B",
		"C",
		"C#",
		"D",
		"D#",
		"E",
		"F",
		"F#",
		"G",
		"G#",
	];

	let currentNote: string = "pick a note";

	function handleClick(note: string) {
		currentNote = note;
	}
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>
<div class="selected-note">
	{currentNote}
</div>
<div class="grid-container">
	{#each notes as note}
		<button on:click={() => handleClick(note)} class="button">
			{note}
		</button>
	{/each}
</div>

<style>
	.selected-note {
		text-align: center;
		font-size: 24px;
		margin-bottom: 20px;
		font-weight: bold;
	}
	.grid-container {
		display: grid;
		grid-template-columns: repeat(12, 1fr); /* 3 columns */
		gap: 10px; /* Gap between buttons */
		padding: 10px;
	}

	.button {
		background-color: #007bff;
		color: white;
		border: none;
		border-radius: 4px;
		padding: 10px;
		text-align: center;
		font-size: 16px;
		cursor: pointer;
		transition: background-color 0.3s;
	}

	.button:hover {
		background-color: #0056b3;
	}
</style>
