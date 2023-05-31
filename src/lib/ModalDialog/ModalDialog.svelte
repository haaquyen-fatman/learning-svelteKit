<script lang="ts">
	import Dialog, { Title, Content, Actions } from '@smui/dialog';
	import Button, { Label } from '@smui/button';

	export let title: string = '';
	export let content: string = '';
	export let leftBtn: string = 'No';
	export let rightBtn: string = 'Yes';
	export let leftBtnDefault: boolean = false;
	export let rightBtnDefault: boolean = false;
	export let open: boolean = false;

	let clicked = 'Nothing yet.';
</script>

<Button on:click={() => (open = true)}>
	<Label>Open Dialog</Label>
</Button>

<Dialog bind:open aria-labelledby="simple-title" aria-describedby="simple-content">
	<Title id="simple-title">{title}</Title>
	<Content id="simple-content">{content}</Content>
	<Actions>
		<Button defaultAction={leftBtnDefault} on:click={() => (clicked = 'No')}>
			<Label>{leftBtn}</Label>
		</Button>
		<Button defaultAction={rightBtnDefault} on:click={() => (clicked = 'Yes')}>
			<Label>{rightBtn}</Label>
		</Button>
	</Actions>
</Dialog>

<pre class="status">Clicked: {clicked}</pre>
