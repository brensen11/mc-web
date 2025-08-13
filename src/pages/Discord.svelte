<script lang="ts">
  const discordInvite = "https://discord.gg/ytyW3GVgCd";
  const channels = [
    {
      name: "#welcome",
      desc: "Where you first land. Rules, server info, and quick links."
    },
    {
      name: "#info",
      desc: "Server Info, a link to this website, and FAQs posted here"
    },
    {
      name: "#announcements",
      desc: "Official updates about the SMP, events, and patch notes."
    },
    {
      name: "#general",
      desc: "Casual place to talk, share memes, and hang out."
    },
    {
      name: "#minecraft-chat",
      desc: "Discord integration with the Minecraft server. A place to chat with players in game, and messages in game will be sent to this chat. Now with images!"
    },
    {
      name: "#screenshot",
      desc: "A place to post and remember moments from Fwends SMP."
    },
    {
      name: "#post",
      desc: "Create Bounties, Quests, Trade offers, Make suggestions and more on through this channel's forms."
    },
    {
      name: "#quests-merits-and-trading",
      desc: "Accept Quests, Jobs, Trades, and more in exchange for coins in game."
    }
  ];
</script>

<main class="flex-1 container mx-auto px-4 py-8 space-y-8">
  <!-- Header -->
  <section class="h-80 flex flex-col items-center justify-center text-center space-y-3">
    <h1 class="text-3xl font-bold">Join the Discord!</h1>
    <p class="text-base-content/80 max-w-lg mx-auto">
      The Fwends SMP Discord is where we coordinate events, chat, and help each other with modded Minecraft.
    </p>
    <a href={discordInvite} target="_blank" rel="noreferrer" class="btn btn-primary">
      Join Now
    </a>
  </section>

  <!-- Features -->
  <section class="card bg-base-200">
    <div class="card-body">
      <h2 class="card-title">Why Join?</h2>
      <ul class="list-disc pl-6 space-y-2">
        <li>Stay up to date on server events & announcements</li>
        <li>Trade items, request help, and find teammates</li>
        <li>Get modpack and technical support</li>
        <li>Hang out with the Fwends community</li>
      </ul>
    </div>
  </section>

  <!-- Channels -->
  <section class="space-y-4">
    <h2 class="text-2xl font-bold">Channel Guide</h2>
    <div class="grid md:grid-cols-2 gap-4">
      {#each channels as c}
        <div class="card bg-base-200">
          <div class="card-body">
            <h3 class="card-title">{c.name}</h3>
            <p class="text-base-content/80">{c.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>
</main>
