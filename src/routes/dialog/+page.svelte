<script lang="ts">
	import ModalDialog from '$lib/ModalDialog/ModalDialog.svelte';
	let showModal: boolean = false;
	let response = 'Nothing yet.';

	function closeHandler(e: CustomEvent<{ action: string }>) {
		switch (e.detail.action) {
			case 'none':
				response = "Ok, well, you're wrong.";
				break;
			case 'all':
				response = 'You are correct. All dogs are the best dog.';
				break;
			default:
				response = "It's a simple question. You should be able to answer it.";
				break;
		}
	}
</script>

<ModalDialog
	open={showModal}
	btnText="Modal dialog"
	title="Testing modal dialog"
	content="Are you okayyyy?"
	leftBtn="Well, not really"
	actionLeft="none"
	rightBtn="Haha"
	leftBtnDefault
	{response}
	{closeHandler}
/>
<pre class="status">Clicked: {response}</pre>
