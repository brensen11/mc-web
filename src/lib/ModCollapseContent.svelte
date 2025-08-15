<script lang="ts">
    import { ExternalLink, TvMinimalPlay } from "lucide-svelte";

    interface ModCollapseContentProps {
        description: string;
        features: string[];
        images: { src: string; alt: string }[];
        wiki?: string;
        tutorial?: string;
    }
    let {
        description,
        features,
        images,
        wiki,
        tutorial,
    }: ModCollapseContentProps = $props();
</script>

<section class="card bg-base-100 border border-base-200">
    <div class="card-body p-4 md:p-5 gap-3">
        <p class="text-sm md:text-base text-base-content/80">
            {description}
        </p>

        <div class="space-x-2">
            {#if wiki}
                <a class="btn btn-primary w-fit" target="_blank" rel="noopener noreferrer" href={wiki}
                    >Wiki <ExternalLink /></a
                >
            {/if}
    
            {#if tutorial}
                <a class="btn btn-primary w-fit" target="_blank" rel="noopener noreferrer" href={tutorial}
                    >Tutorial <TvMinimalPlay /></a>
            {/if}
        </div>

        <h2 class="text-md font-bold">Main Features:</h2>
        <ul class="list-disc pl-5 text-sm md:text-base space-y-1">
            {#each features as feature}
                <li>{feature}</li>
            {/each}
        </ul>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            {#each images as image}
                <img class="rounded-md w-full" src={image.src} alt={image.alt} />
            {/each}
        </div>
    </div>
</section>
