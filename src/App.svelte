<svelte:options tag="my-app"/>
<script>
	export let contents = "We and third parties use cookies to enhance your experience, analyze site performance and monitor web traffic.By visiting our site, you consent to use of cookies.";
	export let learnmorelink = "#";
	export let dismisstext = "DISMISS";
	let show = true;

	function handleDismiss() {
		show = false;
	}
</script>

{#if show}	
<div class="cookie-consent-wrapper">
	<div class="cookie-consent-root">
		<div class="cookie-consent-text">
			{contents}
			 <a href={learnmorelink}>Learn More</a>
		</div>
		<button on:click={handleDismiss} class="cookie-consent-close-btn">{dismisstext}</button>
	</div>
</div>
{/if}

<style>
	.cookie-consent-wrapper {
		position: fixed;
		bottom: 0;
		left: 0;
		right: 0;
		padding: 1em;
		box-sizing: border-box;
		background-color: #333;
		color: white;
	}
	
	.cookie-consent-root {
		max-width: 640px;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.cookie-consent-root a {
		color: white;
	}

	.cookie-consent-close-btn {
		background: transparent;
		color: white;
		border: 1px solid white;
		border-radius: 3px;
		padding: .5em;
	}

	@media (min-width: 640px) {
		
	}
</style>