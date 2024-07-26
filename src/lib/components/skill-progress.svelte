<script lang="ts">
    import { Progress } from "$lib/components/ui/progress";

    let { value, name } = $props<{value: Number, name: string}>();

</script>


    <div class="flex flex-col">
        <div class="flex">
        <div class="font-bold w-full">{name}</div> 
        <div class="font-bold">{value}%</div> 
        </div>
        <Progress value={value} class="bg-accent h-2"/>
    </div>
