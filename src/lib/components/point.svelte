<script lang="ts">

	import { Check, Link } from "lucide-svelte";
	import { PointType } from "../../interfaces.ts/point-type";

    let { children, type } = $props<{children: any, type?: PointType}>();

</script>
<div class="flex">
    {#if type === PointType.Link}
        <Link class="min-w-6 text-accent-foreground mr-2" />
    {:else}
        <Check class="min-w-6 text-accent-foreground mr-2" />
    {/if}
    {@render children()}
</div>