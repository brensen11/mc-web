<script lang="ts">
    import { link } from 'svelte-spa-router'

    interface Props {
        navLinks: {
            label: string;
            path: string;
        }[]
    };
    let { navLinks } : Props = $props();
</script>

<div class="navbar justify-center p-5 gap-10">
    {#each navLinks as navLink}
        <div class="navbar-center">
            <a class="btn btn-ghost p-5 text-xl" href={navLink.path} use:link>{navLink.label}</a>
        </div>
    {/each}
</div>
