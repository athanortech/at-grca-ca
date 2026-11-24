<script lang="ts">
	import type { ActionData, PageData } from './$types';
	import Logo from '#lib/components/Logo/Logo.svelte';
	import Greetings from './Greetings.svelte';
	import FormCard from './FormCard.svelte';
	import { m } from '#paraglide/messages.js';

	interface Props {
		data: PageData;
		form: ActionData;
	}

	let { data, form }: Props = $props();
</script>

<svelte:head>
	<title>AT-GRCA | {m.login()}</title>
</svelte:head>

<main class="lg:relative h-screen bg-surface-200-800">
	<div class="lg:absolute top-5 lg:left-5 flex justify-center">
		<div class="flex justify-center flex-row max-w-48 space-x-4 pb-3">
			<Logo />
		</div>
	</div>
	<div
		class="lg:absolute lg:top-1/2 lg:left-1/2 w-full transform lg:-translate-x-1/2 lg:-translate-y-1/2"
	>
		<div class="flex flex-col lg:flex-row w-full lg:pr-8 space-y-4 lg:space-y-0 lg:space-x-4">
			<Greetings />
			<div class="flex justify-center lg:pr-5 items-center w-full lg:w-2/5">
				<FormCard {data} {form} />
			</div>
		</div>
	</div>
	<!-- AT-GRCA: crédito a CISO Assistant y enlace al código fuente (AGPL-3.0) -->
	<p
		class="lg:absolute bottom-3 inset-x-0 text-center text-xs text-surface-600-400 px-4 py-4 lg:py-0"
	>
		{m.atgrcaPoweredBy()}
		<a
			href="https://github.com/athanortech/at-grca-ca"
			target="_blank"
			rel="noopener noreferrer"
			class="underline hover:text-primary-600-400">{m.atgrcaSourceCode()}</a
		>
	</p>
</main>
