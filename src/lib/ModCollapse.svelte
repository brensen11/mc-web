<script lang="ts">
    import { ChevronDown, ChevronUp } from "lucide-svelte";
    let checked = $state(false);
    interface ModCollapseProps {
        children?: any;
        imgSrc: string;
        modname: string;
        description: string
    }

    let { children, imgSrc, modname, description }: ModCollapseProps = $props();
</script>

<div class="collapse bg-base-300 border-base-300 border">
    <input type="checkbox" bind:checked />
    <div class="collapse-title font-semibold p-4">
        <div class="flex flex-row items-center gap-4">
            <img
                src={imgSrc}
                alt={modname}
                class="w-10 h-10 rounded object-contain"
            />
            <div class="flex flex-row flex-1 justify-between">
                <div class="flex flex-col">
                    {modname}
                    <div class="text-xs md:text-sm font-normal">{description}</div>
                </div>
            </div>
            {#if checked}
                <ChevronUp />
            {:else}
                <ChevronDown />
            {/if}
        </div>
    </div>
    <div class="collapse-content text-sm">
        {@render children?.()}
    </div>
</div>
