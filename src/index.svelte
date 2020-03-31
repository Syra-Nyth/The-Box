<h1 class="title">The Box</h1>

<script>
  let box = {
    locked: true,
    contents: [
        "Fancy pen",
        "Phone charger",
        "Lego model",
        "Chocolate bar",
        "Polyhedral dice set",
        "Lollipop",
        "Tic Tac's"
    ]
  }
	
	const lock = () => {
		box.locked = true
	}
		
	const unlock = () => {
		box.locked = false
	}
</script>

<div class="section">
    {#if box.locked}
        <p>The box is locked.</p>
    <button on:click={unlock}>Unlock & Open</button>
    {:else}
    <p>The box is unlocked.</p>
    <button on:click={lock}>Close & Lock</button>
    {/if}
</div>

<div class="section">
    <h2 class="subtitle">Contents:</h2>
    {#if box.locked}
        <p>Can't open!</p>
    {:else}
        <ul>
            {#each box.contents as item}
                <li>{item}</li>
            {/each}
        </ul>
    {/if}
</div>
