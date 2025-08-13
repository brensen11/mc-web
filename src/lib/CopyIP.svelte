<script>
    const serverIp = "play.brensenvillegas.com";
    import { fade } from "svelte/transition";
    import { Copy, Check } from "lucide-svelte";
    let props = $props();

    let copied = $state(false);

    function copyIp() {
        navigator.clipboard.writeText(serverIp).then(() => {
            copied = true;
            setTimeout(() => (copied = false), 1500);
        });
    }
</script>

<div
    class="relative badge bg-base-200 h-fit p-0 shadow flex flex-row justify-between rounded-2xl {props.class}"
>
    <div>
        <code class="px-4 text-sm font-mono font-light md:text-xl text-lime-500"
            >{serverIp}</code
        >
    </div>
    <button
        class="btn btn-primary rounded-2xl relative"
        onclick={copyIp}
        aria-label="Copy Minecraf IP Address"
    >
        <span class="relative inline-block w-6 h-6 shrink-0">
            <Copy
                size={24}
                class="absolute inset-0 transition-opacity duration-150 {copied
                    ? 'opacity-0'
                    : ''}"
                aria-hidden={copied}
            />
            <Check
                size={24}
                class="absolute inset-0 transition-opacity duration-150 {copied
                    ? ''
                    : 'opacity-0'}"
                aria-hidden={!copied}
            />
        </span>
    </button>
</div>
