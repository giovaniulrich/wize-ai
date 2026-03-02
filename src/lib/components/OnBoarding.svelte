<script>
	import { getContext } from 'svelte';
	import { WEBUI_BASE_URL } from '$lib/constants';

	const i18n = getContext('i18n');

	export let show = true;
	export let getStartedHandler = () => {};
</script>

{#if show}
	<div class="w-full h-screen max-h-[100dvh] text-white relative">
		<div
			class="w-full h-full absolute top-0 left-0 bg-cover bg-center"
			style="background-image: url('{WEBUI_BASE_URL}/static/backscreen.png')"
		></div>
		<div class="w-full h-full absolute top-0 left-0 bg-black/50"></div>

		<div class="relative bg-transparent w-full h-screen max-h-[100dvh] flex z-10">
			<div class="flex w-full items-end justify-center pb-10">
				<button
					class="px-6 py-2 rounded-full bg-white/10 hover:bg-white/20 transition font-medium text-sm"
					on:click={() => {
						getStartedHandler();
					}}
				>
					{$i18n.t(`Get started`)}
				</button>
			</div>
		</div>
	</div>
{/if}
