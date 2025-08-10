<script lang="ts">
    import { onMount } from "svelte";
    import logoBanner from "../assets/img/logo-banner.png";

    const getRandomVideo = () => {
        const part = Math.floor(Math.random() * 14);
        let videoSrc = `/video/segment_0${part < 10 ? '0' : ''}${part}.mp4`;
        return videoSrc;
    }
    const videoSrc = getRandomVideo()

    const serverIp = "play.brensenvillegas.com";
    const discordLink = "https://discord.gg/your-server";
    const bluemapUrl = "https://map.yourserver.com";
    const modpackLink = "https://modrinth.com/modpack/your-pack";

    let serverStatus: string = "Loading...";
    let playersOnline: string[] = [];

    // onMount(async () => {
    //     try {
    //         const res = await fetch("https://api.mcsrvstat.us/2/" + serverIp);
    //         const data = await res.json();
    //         if (data.online) {
    //             serverStatus = `Online (${data.players.online}/${data.players.max})`;
    //             playersOnline = data.players.list || [];
    //         } else {
    //             serverStatus = "Offline";
    //         }
    //     } catch {
    //         serverStatus = "Unavailable";
    //     }
    // });

    let videoElement: HTMLVideoElement;
    onMount(() => {
        videoElement.addEventListener("loadedmetadata", () => {
            const randomTime = Math.random() * (videoElement.duration - 20);
            videoElement.currentTime = randomTime;
        });

        videoElement.addEventListener("ended", () => {
            videoElement.src = getRandomVideo();
            videoElement.play();
        })
    });

    function copyIp() {
        navigator.clipboard.writeText(serverIp);
    }
</script>

<div class="absolute h-svh inset-0 -z-10 pointer-events-none">
    <video
        bind:this={videoElement}
        class="w-full h-full object-cover"
        muted
        autoplay
        playsinline
        preload="metadata"
    >
        <source src={videoSrc} type="video/mp4" />
    </video>
    <div class="absolute inset-0 bg-base-100/40 backdrop-blur-tiny"></div>
    <div
        class="absolute inset-0 bg-linear-to-b from-transparent to-base-100"
    ></div>
</div>

<main class="flex flex-col flex-1 justify-around align-middle p-4 max-w-screen-sm mx-auto relative">
    <img class="wave" src={logoBanner} alt="logo banner" />
    <div class="flex justify-center">
        <!-- <div class="relative badge bg-base-200 py-6 px-20 shadow flex-row justify-center">
            <code class="font-mono font-light text-xl text-lime-500">{serverIp}</code>
            <button
                class="btn btn-primary absolute right-1"
                on:click={copyIp}
                aria-label="Copy Minecraf IP Address"
            >
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    viewBox="0 0 24 24"
                    fill="none"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    class="lucide lucide-copy-icon lucide-copy"
                    ><rect
                        width="14"
                        height="14"
                        x="8"
                        y="8"
                        rx="2"
                        ry="2"
                    /><path
                        d="M4 16c-1.1 0-2-.9-2-2V4c0-1.1.9-2 2-2h10c1.1 0 2 .9 2 2"
                    /></svg
                >
            </button>
        </div> -->
    </div>

    <!-- Insert Future Content -->
    <!-- {#each Array.from({length:300}, (_, i) => i) as i}
        <div>Item {i}</div>
    {/each} -->
</main>

<style>
    .wave {
        animation: wave 2s ease-in-out infinite alternate;
    }
    @keyframes wave {
        0% {
            transform: translateY(-20%);
        }
        100% {
            transform: tranlsateY(20%);
        }
    }

    .backdrop-blur-tiny {
        backdrop-filter: blur(2px);
    }
</style>
