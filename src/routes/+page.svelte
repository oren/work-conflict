<script>
	import { useChat } from 'ai/svelte'

	const { input, handleSubmit, messages } = useChat()
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>Reduce conflcits at work</h1>
	<h2>Prepare a script for a difficult conversation at work. 1 minute, 5 steps.</h2>
	<ul>
		{#each $messages as message}
			<li>{message.role}: {message.content}</li>
		{/each}
	</ul>
	<p>Step 1: Think of a recent conflict with a co-worker. Enter their name.</p>
	<form on:submit={handleSubmit}>
		<input bind:value={$input} />
		<div class="container">
			<button type="submit">Send</button>
		</div>
	</form>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}
	h2 {
		margin-top: -10px;
		text-align: center;
		font-size: 1.3rem;
		margin-bottom: 0px;
	}
	button {
		margin-top: 10px;
		text-align: center;
	}
	p {
		text-align: center;
	}
	.container {
		display: flex;
		justify-content: center; /* center horizontally */
		align-items: center; /* center vertically */
	}
</style>
