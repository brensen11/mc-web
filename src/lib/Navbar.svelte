<script lang="ts">
    import { link } from 'svelte-spa-router'
    import { location } from "svelte-spa-router";

    interface Props {
        navLinks: {
            label: string;
            path: string;
        }[]
    };
    let { navLinks } : Props = $props();
    let drawerOpen = $state(false);
</script>

<div class="hidden md:flex navbar justify-center p-5 gap-10">
    {#each navLinks as navLink}
        <div class="navbar-center">
            <a class="btn btn-ghost p-5 text-xl" href={navLink.path} use:link>{navLink.label}</a>
        </div>
    {/each}
</div>

<div class="drawer md:hidden">
    <input id="menu-drawer" type="checkbox" class="drawer-toggle" bind:checked={drawerOpen} />
    <div class="drawer-content">
        <label for="menu-drawer" class="btn btn-ghost mt-2 ml-2 bg-base-200/50 border-base-100/30 p-3 text-lg"> <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-menu-icon lucide-menu"><path d="M4 12h16"/><path d="M4 18h16"/><path d="M4 6h16"/></svg> Menu</label>
    </div>
        <div class="drawer-side">
        <label for="menu-drawer" aria-label="close sidebar" class="drawer-overlay"></label>
        <ul class="menu bg-base-200 text-base-content min-h-full w-52 p-4">
            {#each navLinks as navLink, i}
            <li><a class="btn my-2 justify-start align-center text-left px-4 py-6 text-lg {$location.endsWith(navLink.path) ? "bg-neutral-800" : ""}" onclick={() => {drawerOpen = false}} href={navLink.path} use:link>{navLink.label}</a></li>
            {#if i !== navLinks.length - 1}
                <hr class="border-t border-neutral-600" />
            {/if}
            {/each}
        </ul>
    </div>
</div>
