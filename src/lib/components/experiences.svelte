<script lang="ts">

	import { Check } from "lucide-svelte";

    let { titre, children } = $props<{titre: string, children?: any}>();

</script>
<div class="bg-card shadow-md rounded-sm p-4 lg:p-4 print:p-2 print:break-inside-avoid-page fixshadowpdf">
    <div class="font-mono font-bold text-2xl text-accent-foreground">{titre}</div>
    <div class="flex flex-col space-y-4 print:space-y-2">
        {@render children()}
    </div>
    
</div>