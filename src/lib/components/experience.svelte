<script lang="ts">

	import { Check } from "lucide-svelte";

    let { titre, societe, debut, fin, children } = $props<{titre: string, societe?: string, debut?: string, fin?: string, children?: any}>();

</script>
<div class="flex-col">
    <div class="flex flex-col lg:flex-row mt-4 print:mt-0">
        <div class="flex-1 flex-col">
            <div class="font-bold text-xl">{titre}</div>
            {#if societe}<div class="font-bold text-muted-foreground">{societe}</div>{/if}
        </div>
        <div class="font-bold font-mono">{debut}{fin && debut ? " - " : ""}{fin}</div>
    </div>
    {#if children}
    <div class="flex flex-col space-y-2 mt-2 print:space-y-1 print:mt-1">
        {@render children()}
    </div>
    {/if}
</div>