<script lang="ts">

	import { Check } from "lucide-svelte";

    let { titre, children } = $props<{titre: string, children?: any}>();

</script>
<div class="bg-card shadow-md rounded-sm p-2 lg:p-4">
    <div class="font-mono font-bold text-2xl">{titre}</div>
    <div class="flex flex-col space-y-4">
        {@render children()}
    </div>
    
</div>