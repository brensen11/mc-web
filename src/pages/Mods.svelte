<script lang="ts">
  import { onMount } from "svelte";
  import ModCollapse from "../lib/ModCollapse.svelte";
  import ModCollapseContent from "../lib/ModCollapseContent.svelte";

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
      icon: "https://media.forgecdn.net/avatars/thumbnails/964/796/64/64/638463179928227673.png",
      short: "Shops, banks, and player economy.",
      desc: "Adds a full economy with currencies, ATMs, player shops, auctions, and buy orders.",
      wiki: "https://github.com/Lightman314/LightmansCurrency/wiki",
      tutorial: "https://www.youtube.com/embed/VIDEO_ID_1",
    },
  ];

  onMount(() => {
    const carousel = document.getElementById("my-carousel");
    carousel?.addEventListener("wheel", (e) => {
      console.log("Scroll! ", e.deltaY, e.deltaX);
      if (e.deltaY === 0) return; // skip if no vertical scroll
      e.preventDefault();
      carousel.scrollBy(e.deltaY, 0);
      // carousel.scrollLeft += e.deltaY; // convert vertical scroll to horizontal
    });
  });
</script>

<!-- Change input type to "checkbox" if you want multiple open at once -->
<main class="flex flex-col items-center container mx-auto p-4">
  <!-- Main Mods -->
  <h1 class="text-3xl font-bold mb-4 self-start">Main Mods</h1>

  <!-- Main Mods collapse list -->
  <div class="flex flex-col gap-2">
    <!-- Apotheosis -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/806/643/64/64/638174667713250064.png"
      modname="Apotheosis"
      description="A mod about getting strong"
    >
      <ModCollapseContent
        description="Apotheosis is a content mod that 
        allows you to become stronger than ever before, while trying to stay true to vanilla mechanics at heart. 
        Every feature is carefully put together to feel cohesive and complete.
        Features range from simple changes, such as the addition of Potion Charms, to massive refactors of vanilla systems, such as Enchanting.
        "
        wiki="https://minecraft-apotheosis-mod.fandom.com/wiki/Minecraft_Apotheosis_Mod_Wiki"
        tutorial="https://www.youtube.com/watch?v=0hnKidZkiV8&ab_channel=Avo"
        features={[
          "New tier and level up system",
          "Overhall to enchanting",
          "New enemies and weapons",
        ]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/1160/35/8-3-0_key_art-jpg.jpg",
            alt: "Apotheosis Altar",
          },
          {
            src: "https://media.forgecdn.net/attachments/903/391/2024-06-29_01.jpg",
            alt: "Apotheosis Library and Enchanting",
          },
          {
            src: "https://i.imgur.com/yEvLHAV.png",
            alt: "Apotheosis leveling up",
          },
        ]}
      />
    </ModCollapse>

    <!-- Applied Energistics 2 -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/1025/127/638548475358792693.webp"
      modname="Applied Energistics 2"
      description="An Inventory Management Mod"
    >
      <ModCollapseContent
        description="Applied Energistics 2 adds components and mechanics to provide logistics and storage solutions. You can replace your massive room full of chests with a compact ME Network, but that's just the beginning of things. Applied Energistics is meant to work with and allow automation of other mods in a modpack. You can set up your system to, with a single click, craft all of the prerequisites (and the final result) of a complex crafting chain, or keep certain quantities of items in stock, crafting more as needed, or simply transfer items around your base."
        wiki="https://guide.appliedenergistics.org/1.21/"
        tutorial="https://www.youtube.com/watch?v=3htUhkDYbJ8&ab_channel=BucketSt"
        features={[
          "Storage System",
          "Auto Crafting",
          "Spatial Storage (Storing Builds)",
        ]}
        images={[
          {
            src: "https://raw.githubusercontent.com/AppliedEnergistics/Applied-Energistics-2/main/docs/demo-scene.png",
            alt: "example ae2 project",
          },
          {
            src: "https://guide-assets.appliedenergistics.org/minecraft-1.20.1/ae2/ae2-mechanics/import-export-storage_scene1.Jml8xiL7aCHQ.png",
            alt: "example storage setup",
          },
        ]}
      />
    </ModCollapse>

    <!-- Ars Nouveau -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/565/915/64/64/637924211543296813.png"
      modname="Ars Nouveau"
      description="A magic and spell crafting mod"
    >
      <ModCollapseContent
        description="Ars Nouveau is a magic mod inspired by Ars Magicka that allows players to craft their own spells, create magical artifacts, perform rituals, and much more. Documentation is provided entirely in-game by Patchouli. To get started with this mod, craft the Worn Notebook using a book and 1 Lapis Lazuli. You can also consult the wiki below."
        wiki="https://www.arsnouveau.wiki/"
        tutorial="https://www.youtube.com/watch?v=kk5rB6iyh_E&ab_channel=JaviHerobrine"
        features={[
          "Spell Crafting",
          "Powerful baubles and trinkets",
          "Magical Mahchines",
          "Automation with magical servants",
        ]}
        images={[
          {
            src: "https://i.ytimg.com/vi/rcnhISDnlZ8/maxresdefault.jpg",
            alt: "Enchanting or something",
          },
          {
            src: "https://images.1v9.gg/Ars%20Nouveau%20minecraft%20mod-ac8044974869.webp",
            alt: "Ars Noveau Farming",
          },
        ]}
      />
    </ModCollapse>

    <!-- Biomes O' Plenty -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/477/194/64/64/637771671789296797.png"
      modname="Biomes O' Plenty"
      description="A mod that adds new biomes"
    >
      <ModCollapseContent
        description="Biomes O' Plenty is an expansive biome mod for Minecraft that adds a slew of new, unique biomes to the Overworld, Nether, and End! To go along with the new biomes, it adds new plants, flowers, trees, building blocks, and much more!"
        wiki="https://biomesoplenty.fandom.com/wiki/Biomes_O%27_Plenty_Wiki"
        features={["New Biomes"]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/680/562/2.png",
            alt: "Wetland and Bog",
          },
          {
            src: "https://media.forgecdn.net/attachments/765/174/3.png",
            alt: "Redwood Forest",
          },
          {
            src: "https://media.forgecdn.net/attachments/1267/587/11-png.png",
            alt: "Overgrown Greens",
          },
          {
            src: "https://media.forgecdn.net/attachments/765/995/17.png",
            alt: "Hot Springs and Snowy Forest",
          },
        ]}
      />
    </ModCollapse>

    <!-- Chipped -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/495/254/64/64/637808243655328652_animated.gif"
      modname="Chipped"
      description="A decorational blocks mod"
    >
      <ModCollapseContent
        description="Chipped is a building mod that expands on the variety of blocks you can use in-game. The mod offers over 11,000 unique building blocks, from stained glass variations all the way to conerete, prismarine and even gilded blackstone! Not only are all the textures hand-made in the vanilla style, but they also include many connected textures."
        features={["New Blocks!"]}
        images={[
          {
            src: "https://cdn.modrinth.com/data/BAscRYKm/images/cbbeeca232f2632aef4ac4856f80c2e7566a4461.png",
            alt: "Image of Carpenter's Workbench",
          },
          {
            src: "https://cdn.modrinth.com/data/BAscRYKm/images/017ffb65c110aa79e55111c945103364d5556203_350.webp",
            alt: "Image of Mason's Workbench",
          },
        ]}
      />
    </ModCollapse>

    <!-- Farmer's Delight -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/396/11/64/64/637595005615179370.png"
      modname="Farmer's Delight"
      description="A Farming and Crops Mod"
    >
      <ModCollapseContent
        description="Farmer's Delight is a mod that gently expands upon farming and cooking in Minecraft. Using a simple cooking system and a few familiar ingredients, you'll be able to prepare a wide variety of hearty meals: from sandwiches to salads and stews, from beautiful desserts to mouth-watering feasts, no ingredient will be left behind in your kitchen!"
        wiki="https://github.com/vectorwing/FarmersDelight/wiki"
        tutorial="https://www.youtube.com/watch?v=PV5g-kx_CPE&ab_channel=EccentricEmerald"
        features={["New Crops", "New Recipes", "New Cooking Items"]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/456/879/basic-crops.png",
            alt: "New Cropts",
          },
          {
            src: "https://media.forgecdn.net/attachments/456/881/kitchenware.png",
            alt: "New Kitchen",
          },
          {
            src: "https://media.forgecdn.net/attachments/456/882/cozy-decorations.png",
            alt: "New Kitchen Again",
          },
          {
            src: "https://media.forgecdn.net/attachments/456/883/glorious-feast.png",
            alt: "Glorious Feast",
          },
        ]}
      />
    </ModCollapse>

    <!-- Immersive Aircraft -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/656/842/64/64/638056986831428322.png"
      modname="Immersive Aircraft"
      description="A mod that adds planes, airships, and more to minecraft"
    >
      <ModCollapseContent
        description="This mod adds a bunch of rustic aircraft to travel, transport, and explore! The aircraft have a strong focus on being vanilla-faithful with many details and functionalities, without being overly complicated."
        wiki="https://www.minecraft-guides.com/mod/immersive-aircraft/"
        tutorial="https://www.youtube.com/watch?v=yllKKe1Az0k&ab_channel=DaveKratzy"
        features={["A Biplane", "An Airship", "A Gyrodyne", "A Quadrocopter"]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/533/937/screen1.png",
            alt: "2 Players in quad copter",
          },
          {
            src: "https://media.forgecdn.net/attachments/533/938/screen4.png",
            alt: "Airplane minecraft pov",
          },
        ]}
      />
    </ModCollapse>

    <!-- Lightman's Currency -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/964/796/64/64/638463179928227673.png"
      modname="Lightman's Currency"
      description="A currency, shop, and trading mod."
    >
      <ModCollapseContent
        description="Lightman's Currency adds an item-based money system to the game through coins, which can be used to trade with your friends in a multiplayer environment."
        wiki="https://github.com/Lightman314/LightmansCurrency/wiki"
        tutorial="https://www.youtube.com/watch?v=B_tm_RzumVM&ab_channel=Farmagician"
        features={[
          "Coins & wallets",
          "Vending Machines",
          "Shop and Sell Systems",
        ]}
        images={[
          {
            src: "https://i.imgur.com/IgWXlMz.png",
            alt: "Scrooge McDuck",
          },
          {
            src: "https://i.imgur.com/IctdD2t.png",
            alt: "Shop",
          },
          {
            src: "https://i.imgur.com/2ns08xo.png",
            alt: "Vending Machines",
          },
          {
            src: "https://i.imgur.com/YbxhIz5.png",
            alt: "More Vending Machines",
          },
        ]}
      />
    </ModCollapse>

    <!-- MrCrayfish's Furniture Mod: Refurbished -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/934/904/64/64/638411339753659456.png"
      modname="MrCrayfish's Furniture Mod: Refurbished"
      description="A furniture and decor mod"
    >
      <ModCollapseContent
        description="Introducing the next generation of MrCrayfish's Furntiure Mod, built from the ground up with brand new blocks, models, original sounds, and gameplay mechanics. Experience the new yet familiar charm of the original mod, and furnish your house with the hundreds of new and original decorational and functional blocks. Jump into new gameplay mechanics with the introduction of the electricity system to power all your appliances and electronics. Take control of the mod, now featuring integration for CraftTweaker and extensive datapack support."
        wiki="https://mrcrayfish.github.io/MrCrayfishFurnitureMod-Refurbished/"
        tutorial="https://www.youtube.com/watch?v=JbbXYh1k3iE&ab_channel=Dimy"
        features={[
          "Adds over 440+ functional and cosmetic blocks to decorate your house!",
          "Over 70+ original sound effects (all recorded and engineered by MrCrayfish) to fulfil your immersion.",
          "A fully functional computer block that has fun and useful apps.",
        ]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/791/961/kitchendemoscreenshot.png",
            alt: "kitchen",
          },
          {
            src: "https://media.forgecdn.net/attachments/792/547/bedroomdemoscreenshot.png",
            alt: "Front room",
          },
          {
            src: "https://media.forgecdn.net/attachments/792/665/outdoordemoscreenshot.png",
            alt: "outdoor patio",
          },
          {
            src: "https://media.forgecdn.net/attachments/793/579/bathroomdemoscreenshot.png",
            alt: "bathroom",
          },
        ]}
      />
    </ModCollapse>

    <!-- Oritech -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/1008/455/64/64/638531232676721475.png"
      modname="Oritech"
      description="A tech and automation mod"
    >
      <ModCollapseContent
        description="Oritech is an open-source tech mod (currently for Minecraft 1.21), featuring many new machines and tools. Content ranges from processing machines, world interaction machines, logistical parts, new features integrated into world generation, equipment, and more. Machines are mostly animated multiblocks, with upgrades being implemented using addon blocks."
        wiki="https://moddedmc.wiki/en/project/oritech/docs"
        tutorial="https://www.youtube.com/watch?v=T0lK4XqXDD0&t=12s&ab_channel=JaviHerobrine"
        features={["Ore processing chains"]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/882/580/drone_port.png",
            alt: "oritech overall",
          },
          {
            src: "https://media.forgecdn.net/attachments/882/581/enderic_laser_digging.png",
            alt: "laser",
          },
          {
            src: "https://media.forgecdn.net/attachments/882/583/farming.png",
            alt: "farming",
          },
          {
            src: "https://media.forgecdn.net/attachments/882/586/oil_processing.png",
            alt: "oil processing",
          },
        ]}
      />
    </ModCollapse>

    <!-- Tom's Simple Storage Mod -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/266/898/64/64/637234057062921445.png"
      modname="Tom's Simple Storage"
      description="A vanilla style simple storage management mod"
    >
      <ModCollapseContent
        description="Simple vanilla style storage mod."
        tutorial="https://www.youtube.com/watch?v=nW5ElcWiC3c&ab_channel=Rockit14"
        features={[
          "Storage & Crafting Terminal",
          "Inventory Connector",
          "Wireless Terminal",
          "Inventory Hoppers",
        ]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/288/563/2020-04-24_18.png",
            alt: "Tom's Simple Storage Mod",
          },
        ]}
      />
    </ModCollapse>

    <!-- When Dungeons Arise -->
    <ModCollapse
      imgSrc="https://media.forgecdn.net/avatars/thumbnails/405/21/64/64/637616382422917614.png"
      modname="When Dungeons Arise"
      description="A dungeon structure mod"
    >
      <ModCollapseContent
        description="When Dungeons Arise is a massive dungeon generator which gathers plenty of dungeons and generates them randomly on your worlds to ensure glorious adventures and challenges. We have took a step away from standard vanilla structures, resulting in imposing dungeons to lose yourself into."
        features={[
          "Massive Dungeons stuctures which spawn natrually in the world."
        ]}
        images={[
          {
            src: "https://media.forgecdn.net/attachments/1065/230/2025-01-08_16.jpg",
            alt: "Large Chinese Tower",
          },
          {
            src: "https://i.postimg.cc/R0gk61Fm/2021-07-11-17-34-23.png",
            alt: "Large sandstone structure"
          }
        ]}
      />
    </ModCollapse>
  </div>
</main>
