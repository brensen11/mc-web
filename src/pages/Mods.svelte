<script lang="ts">
  type Mod = {
    name: string;
    icon: string;
    short: string;
    desc: string;
    wiki?: string;
    tutorial?: string; // YouTube embed URL
  };

  const mods: Mod[] = [
    {
      name: "Lightman's Currency",
      icon: "/icons/lightmans_currency.png",
      short: "Shops, banks, and player economy.",
      desc: "Adds a full economy with currencies, ATMs, player shops, auctions, and buy orders.",
      wiki: "https://github.com/Lightman314/LightmansCurrency/wiki",
      tutorial: "https://www.youtube.com/embed/VIDEO_ID_1"
    },
    {
      name: "Waystones",
      icon: "/icons/waystones.png",
      short: "Craftable fast-travel network.",
      desc: "Place waystones and use scrolls/warps to travel. Server-friendly and configurable.",
      wiki: "https://wiki.blay09.net/wiki/Waystones",
      tutorial: "https://www.youtube.com/embed/VIDEO_ID_2"
    },
    {
      name: "Alex's Mobs",
      icon: "/icons/alexs_mobs.png",
      short: "Dozens of new creatures.",
      desc: "A bestiary of unique mobs with drops, behavior, and boss encounters.",
      wiki: "https://github.com/Alex-the-666/AlexsMobs/wiki"
    }
  ];
</script>

<!-- Change input type to "checkbox" if you want multiple open at once -->
<div class="space-y-3">
  {#each mods as mod, i}
    <div class="collapse collapse-arrow bg-base-200">
      <input type="radio" name="mods-accordion" checked={i === 0} />
      <div class="collapse-title flex items-center gap-3">
        <img src={mod.icon} alt={mod.name} class="w-10 h-10 rounded object-contain" />
        <div class="min-w-0">
          <h3 class="font-semibold truncate">{mod.name}</h3>
          <p class="text-sm text-base-content/70 line-clamp-1">{mod.short}</p>
        </div>
      </div>
      <div class="collapse-content space-y-3">
        <p class="text-base-content/80">{mod.desc}</p>

        <div class="flex flex-wrap gap-2">
          {#if mod.wiki}
            <a href={mod.wiki} target="_blank" rel="noreferrer" class="btn btn-sm btn-primary">Wiki</a>
          {/if}
          {#if mod.tutorial}
            <a href={mod.tutorial} target="_blank" rel="noreferrer" class="btn btn-sm">Tutorial</a>
          {/if}
        </div>

        {#if mod.tutorial}
          <div class="aspect-video rounded-box overflow-hidden">
            <iframe
              class=""
              src={mod.tutorial}
              title={`${mod.name} Tutorial`}
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              allowfullscreen
            />
          </div>
        {/if}
      </div>
    </div>
  {/each}
</div>
