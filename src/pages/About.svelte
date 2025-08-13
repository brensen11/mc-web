<script lang="ts">
  const name = "Brensen";
  const tagline = "CS grad • Builder • Modded Minecraft enjoyer";

  // Inline SVGs (Tailwind-sized). Add/modify as needed.
  const icons: Record<string, string> = {
    default: `<span class="w-5 h-5">★</span>`,
    github: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="currentColor"><path d="M12 .5a12 12 0 0 0-3.79 23.4c.6.11.82-.26.82-.58v-2.03c-3.34.73-4.04-1.61-4.04-1.61-.55-1.38-1.35-1.75-1.35-1.75-1.1-.76.08-.75.08-.75 1.22.09 1.86 1.25 1.86 1.25 1.08 1.86 2.84 1.32 3.53 1.01.11-.79.42-1.32.76-1.62-2.66-.3-5.46-1.33-5.46-5.93 0-1.31.47-2.39 1.24-3.24-.12-.3-.54-1.52.12-3.16 0 0 1.01-.32 3.3 1.24a11.5 11.5 0 0 1 6 0c2.28-1.56 3.29-1.24 3.29-1.24.67 1.64.25 2.86.12 3.16.77.85 1.24 1.93 1.24 3.24 0 4.61-2.8 5.62-5.47 5.92.43.38.81 1.12.81 2.26v3.35c0 .32.21.7.82.58A12 12 0 0 0 12 .5Z"/></svg>`,
    discord: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="currentColor"><path d="M20 4a16 16 0 0 0-4-1l-.19.37A13 13 0 0 1 12 3c-1.3 0-2.56.18-3.81.54L8 3a16 16 0 0 0-4 1C1.55 6.64 1 9.2 1 11.73 1 17.1 4.47 19 7.87 20l.47-.95a8.5 8.5 0 0 1-1.32-.65l.3-.22c.86.4 1.8.69 2.77.85a14 14 0 0 0 3.82 0 10 10 0 0 0 2.78-.85l.3.22c-.42.26-.86.48-1.32.65l.47.95C19.53 19 23 17.1 23 11.73 23 9.2 22.45 6.64 20 4ZM9.75 14.5c-.77 0-1.4-.75-1.4-1.67 0-.93.63-1.68 1.4-1.68s1.4.75 1.4 1.68c0 .92-.63 1.67-1.4 1.67Zm4.5 0c-.77 0-1.4-.75-1.4-1.67 0-.93.63-1.68 1.4-1.68s1.4.75 1.4 1.68c0 .92-.63 1.67-1.4 1.67Z"/></svg>`,
    mail: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><path stroke-width="2" d="M4 6h16v12H4z"/><path stroke-width="2" d="m4 6 8 7 8-7"/></svg>`,
    svelte: `<svg viewBox="0 0 256 256" class="w-5 h-5" fill="currentColor"><path d="M128 24c57 0 104 47 104 104s-47 104-104 104S24 185 24 128 71 24 128 24Z"/></svg>`,
    tailwind: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="currentColor"><path d="M12 6c-2.67 0-4.33 1.33-5 4 1-.67 2-1 3-1 2 0 3 .67 4 2 1 1.33 2 2 4 2 2 0 3-.67 4-2-1 .67-2 1-3 1-2 0-3-.67-4-2-1-1.33-2-2-4-2Zm-7 6c-2.67 0-4.33 1.33-5 4 1-.67 2-1 3-1 2 0 3 .67 4 2 1 1.33 2 2 4 2 2 0 3-.67 4-2-1 .67-2 1-3 1-2 0-3-.67-4-2-1-1.33-2-2-4-2Z"/></svg>`,
    sparkles: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><path stroke-width="2" d="M12 3l2 4 4 2-4 2-2 4-2-4-4-2 4-2 2-4Zm6 11 1 2 2 1-2 1-1 2-1-2-2-1 2-1 1-2Z"/></svg>`,
    ts: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="currentColor"><path d="M3 4h18v16H3z"/><path fill="#fff" d="M7 9h6v2H11v6H9v-6H7zm9 1.8c-.9 0-1.5.4-1.9 1l1.6.9c.1-.3.3-.6.7-.6.4 0 .6.2.6.5 0 .3-.2.5-.8.7-1 .4-1.6 1-1.6 2.1 0 1.4 1.1 2.1 2.3 2.1 1 0 1.7-.4 2.2-1.1l-1.4-1c-.2.3-.4.5-.8.5-.3 0-.6-.2-.6-.5 0-.3.2-.5.8-.7 1-.4 1.6-1 1.6-2.1 0-1.3-1-2.1-2.7-2.1Z"/></svg>`,
    cloud: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><path stroke-width="2" d="M7 18h10a4 4 0 0 0 0-8 6 6 0 0 0-11-2A4 4 0 0 0 7 18Z"/></svg>`,
    server: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><rect x="3" y="4" width="18" height="6" rx="2" stroke-width="2"/><rect x="3" y="14" width="18" height="6" rx="2" stroke-width="2"/><path stroke-width="2" d="M7 7h.01M7 17h.01"/></svg>`,
    blocks: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><rect x="3" y="3" width="7" height="7" stroke-width="2"/><rect x="14" y="3" width="7" height="7" stroke-width="2"/><rect x="3" y="14" width="7" height="7" stroke-width="2"/></svg>`,
    book: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><path stroke-width="2" d="M4 5h12a3 3 0 0 1 3 3v11H7a3 3 0 0 1-3-3z"/><path stroke-width="2" d="M7 5v11"/></svg>`,
    zap: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><path stroke-width="2" d="M13 3 4 14h7l-1 7 9-11h-7z"/></svg>`,
    link: `<svg viewBox="0 0 24 24" class="w-5 h-5" fill="none" stroke="currentColor"><path stroke-width="2" d="M10 13a5 5 0 0 1 0-7l1-1a5 5 0 0 1 7 7l-1 1M14 11a5 5 0 0 1 0 7l-1 1a5 5 0 0 1-7-7l1-1"/></svg>`
  };

  const socials = [
    { label: "GitHub", href: "https://github.com/yourname", icon: "github" },
    { label: "Discord", href: "https://discord.gg/YOUR_INVITE", icon: "discord" },
    { label: "Email", href: "mailto:you@example.com", icon: "mail" }
  ];

  const stack = [
    { name: "SvelteKit", icon: "svelte", note: "Site & UI" },
    { name: "TailwindCSS", icon: "tailwind", note: "Design system" },
    { name: "DaisyUI", icon: "sparkles", note: "Components" },
    { name: "TypeScript", icon: "ts", note: "Typed everywhere" },
    { name: "Cloudflare Pages", icon: "cloud", note: "Hosting" },
    { name: "R2 / Workers", icon: "server", note: "Assets & glue" }
  ];

  const highlights = [
    { title: "Fwends SMP", desc: "Community modded server with economy & QoL.", icon: "blocks" },
    { title: "Helpful Docs", desc: "Join guides, mod cards, quick troubleshooting.", icon: "book" },
    { title: "Fast & Simple", desc: "Minimal bloat, quick load, accessible UI.", icon: "zap" }
  ];

  const timeline = [
    { year: "2025", text: "Launched Fwends SMP + site refresh." },
    { year: "2024", text: "Built SvelteKit projects; deployed on Cloudflare." },
    { year: "2023", text: "Wrapped up CS master’s; focused on dev tooling." }
  ];

  const faqs = [
    { q: "What stack do you prefer?", a: "SvelteKit + Tailwind + DaisyUI for speed, CF Pages for hosting." },
    { q: "Open to collabs?", a: "Yep—modded MC, web tooling, or lightweight apps." },
    { q: "How to reach you?", a: "Discord is fastest; email works too." }
  ];
</script>

<main class="flex-1 container mx-auto px-4 py-10 space-y-10">
  <!-- Hero -->
  <section class="min-h-[40vh] flex flex-col items-center justify-center text-center gap-4">
    <h1 class="text-4xl font-bold">{name}</h1>
    <p class="text-base-content/80">{tagline}</p>
    <div class="flex flex-wrap items-center justify-center gap-3">
      {#each socials as s}
        <a class="btn btn-sm gap-2" href={s.href} target="_blank" rel="noreferrer">
          {@html (icons[s.icon] || icons.default)}
          <span>{s.label}</span>
        </a>
      {/each}
    </div>
  </section>

  <!-- Framework & Stack -->
  <section class="card bg-base-200">
    <div class="card-body">
      <h2 class="card-title">Framework & Stack</h2>
      <p class="text-base-content/80">
        Built for speed and simplicity. Static-friendly, cacheable, and minimal JS on page.
      </p>
      <div class="mt-4 grid sm:grid-cols-2 lg:grid-cols-3 gap-3">
        {#each stack as s}
          <div class="flex items-center gap-3 p-3 rounded-box bg-base-100">
            {@html (icons[s.icon] || icons.default)}
            <div class="min-w-0">
              <div class="font-semibold">{s.name}</div>
              <div class="text-sm text-base-content/70">{s.note}</div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <!-- Highlights -->
  <section class="grid md:grid-cols-3 gap-4">
    {#each highlights as h}
      <div class="card bg-base-200">
        <div class="card-body">
          <div class="flex items-center gap-2">
            {@html (icons[h.icon] || icons.default)}
            <h3 class="card-title">{h.title}</h3>
          </div>
          <p class="text-base-content/80">{h.desc}</p>
        </div>
      </div>
    {/each}
  </section>

  <!-- About Me -->
  <section class="card bg-base-200">
    <div class="card-body">
      <h2 class="card-title">About Me</h2>
      <p class="text-base-content/80">
        I’m {name}. I like building fast, tidy tools and hosting community servers.
        Lately: SvelteKit sites, Cloudflare Pages deploys, and a modded SMP with economy & QoL.
      </p>
      <div class="mt-3 flex flex-wrap gap-2">
        <span class="badge">SvelteKit</span>
        <span class="badge">TypeScript</span>
        <span class="badge">Tailwind</span>
        <span class="badge">DaisyUI</span>
        <span class="badge">Cloudflare</span>
      </div>
    </div>
  </section>

  <!-- Timeline -->
  <section class="card bg-base-200">
    <div class="card-body">
      <h2 class="card-title">Timeline</h2>
      <ul class="timeline timeline-vertical">
        {#each timeline as t}
          <li>
            <div class="timeline-start">{t.year}</div>
            <div class="timeline-middle">{@html icons.sparkles}</div>
            <div class="timeline-end timeline-box bg-base-100">{t.text}</div>
          </li>
        {/each}
      </ul>
    </div>
  </section>

  <!-- FAQ -->
  <section class="space-y-3">
    <h2 class="text-2xl font-bold">FAQ</h2>
    {#each faqs as f}
      <div class="collapse bg-base-200">
        <input type="checkbox" />
        <div class="collapse-title text-lg font-medium flex items-center gap-2">
          {@html icons.book}
          {f.q}
        </div>
        <div class="collapse-content text-base-content/80">
          <p>{f.a}</p>
        </div>
      </div>
    {/each}
  </section>

  <!-- Contact -->
  <section class="card bg-base-200">
    <div class="card-body">
      <h2 class="card-title">Get in Touch</h2>
      <div class="flex flex-wrap gap-3">
        {#each socials as s}
          <a class="btn gap-2" href={s.href} target="_blank" rel="noreferrer">
            {@html (icons[s.icon] || icons.default)}
            <span>{s.label}</span>
          </a>
        {/each}
      </div>
    </div>
  </section>
</main>
