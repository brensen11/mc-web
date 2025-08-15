<script lang="ts">
    import { onMount } from "svelte";
    import logoBanner from "../assets/img/FwendsSMP.png";
    import CopyIp from "../lib/CopyIP.svelte";

    const getRandomVideo = () => {
        const part = Math.floor(Math.random() * 14);
        let videoSrc = `/video/segment_0${part < 10 ? "0" : ""}${part}.mp4`;
        return videoSrc;
    };
    const videoSrc = getRandomVideo();

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
        });
    });

    let title = "Fwends SMP TEST";
    let description = "Welcome to the Fwends Survial Multiplayer Server!";
    let image = "../assets/img/Fwends SMP Page Preview.png";
    let url = "http://mc.brensenvillegas.com";
</script>

<svelte:head>
    <meta property="og:title" content={title} />
    <meta property="og:description" content={description} />
    <meta property="og:image" content={image} />
    <meta property="og:url" content={url} />
    <meta property="og:type" content="website" />
</svelte:head>

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
        class="absolute bottom-0 left-0 right-0 h-48 bg-linear-to-b from-transparent to-base-100"
    ></div>
</div>

<main
    class="flex flex-col flex-1 justify-around align-middle max-w-screen-sm p-4 mx-auto relative"
>
    <!-- banner -->
    <img class="wave" src={logoBanner} alt="logo banner" />

    <!-- copy IP -->
    <div class="flex justify-center">
        <CopyIp />
    </div>
</main>

<style>
    .wave {
        animation: wave 2s ease-in-out infinite alternate;
    }
    @keyframes wave {
        0% {
            transform: translateY(-10%);
        }
        100% {
            transform: tranlsateY(10%);
        }
    }

    .backdrop-blur-tiny {
        backdrop-filter: blur(2px);
    }
</style>
