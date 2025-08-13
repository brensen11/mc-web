<script lang="ts">
    const serverIP = "play.brensenvillegas.com";
    const prismUrl = "https://prismlauncher.org/download/windows/";
    const guideUrl =
        "https://www.youtube.com/embed/CA2fdUzChCo?si=f1mngDrcA1D_Ci9-";
    const modpackUrl = "https://drive.usercontent.google.com/download?id=1XNMC0IwlOyvamvUq1iabvUOcsQ2xGfOX&export=download&authuser=0"; // replace

    import installSrc from "../assets/img/Install.png";
    import ramSrc from "../assets/img/RAM.png";
    import CopyIp from "../lib/CopyIP.svelte";
    import { Download } from 'lucide-svelte'
    const addServerSrc = "/AddServer.gif";

</script>

<main class="flex-1 container mx-auto px-4 py-8 space-y-8">
    <section class="flex flex-col items-center text-center space-y-3">
        <h1 class="text-3xl font-bold">How to Join Fwends SMP</h1>
        <p class="text-base-content/80">
            Welcome! Fwends is a Forge modpack. Follow these quick steps to get
            in.
        </p>

        <CopyIp />
    </section>

    <div class="grid lg:grid-cols-3 gap-6">
        <aside class="hidden lg:grid sticky top-4 lg:col-span-1 h-fit">
            <ul class="steps steps-vertical w-full">
                <li class="step step-primary">Download Prism</li>
                <li class="step step-primary">Get the Modpack</li>
                <li class="step step-primary">Import into Prism</li>
                <li class="step step-primary">Tweak Options</li>
                <li class="step step-primary">Launch & Connect</li>
            </ul>
            <div class="mt-6 card bg-base-200">
                <div class="card-body space-y-2">
                    <h3 class="card-title text-base">Quick Info</h3>
                    <p>
                        <span class="font-semibold">Version:</span> Minecraft 1.21.1
                        (Forge)
                    </p>
                    <p>
                        <span class="font-semibold">Server IP:</span>
                        {serverIP}
                    </p>
                </div>
            </div>
        </aside>

        <div class="lg:col-span-2 space-y-6">
            <!-- Prism Launcher -->
            <section class="card bg-base-200">
                <div class="card-body">
                    <h2 class="card-title">
                        1) How to download Prism Launcher
                    </h2>
                    <p class="text-base-content/80">
                        Prism Launcher is the easiest way to manage modded
                        instances.
                    </p>
                    <div class="flex flex-wrap gap-3 my-3">
                        <a
                            href={prismUrl}
                            target="_blank"
                            rel="noreferrer"
                            class="btn btn-primary">Download Prism <Download /> </a
                        >
                    </div>
                    <p class="text-base-content/80">
                        Here's a short video explaining a bit more about Prism
                        if you need
                    </p>
                    <iframe
                        class="rounded-md md:w-[530px] h-[315px]"
                        src={guideUrl}
                        title="YouTube video player"
                        frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                        referrerpolicy="strict-origin-when-cross-origin"
                        allowfullscreen
                    ></iframe>
                </div>
            </section>

            <!-- Download Modpack -->
            <section class="card bg-base-200">
                <div class="card-body">
                    <h2 class="card-title">2) Download Mods</h2>
                    <p class="text-base-content/80">
                        Grab the prebuilt modpack zip (no need to unzip).
                    </p>
                    <a href={modpackUrl} target="_blank" rel="noreferrer" class="btn btn-primary w-fit"
                        >Download <code>fwends_modpack.zip</code> <Download /> </a
                    >
                </div>
            </section>

            <!-- Import -->
            <section class="card bg-base-200">
                <div class="card-body">
                    <h2 class="card-title">3) Add modpack to Prism</h2>
                    <ol class="list-decimal pl-6 space-y-2">
                        <li>Open Prism Launcher.</li>
                        <li>
                            Click <span class="badge">Add Instance</span> →
                            <span class="badge">Import</span> →
                            <span class="badge">Browse</span>
                        </li>
                        <li>
                            Select the downloaded <code class="badge"
                                >fwends_modpack.zip</code
                            > and confirm.
                        </li>
                    </ol>
                    <div class="flex flex-col my-4 gap-4 items-center w-full">
                        <img
                            class="w-[90%]"
                            src={installSrc}
                            alt="Add Instance to Prism"
                        />
                    </div>
                </div>
            </section>

            <!-- Options -->
            <section class="card bg-base-200">
                <div class="card-body">
                    <h2 class="card-title">4) Options</h2>
                    <ul class="list-disc pl-6 space-y-2">
                        <li>
                            <span class="badge"
                                >Settings</span
                            >
                            → <span class="badge">Java</span> →
                            <span class="badge">Maximum memory allocation</span>
                            <div class="mt-2">Set <span class="font-semibold">Maximum Memory</span>:</div>
                            <div class="mt-2 grid grid-cols-3 gap-2 max-w-md">
                                <kbd class="kbd">4 GB (4096 MiB)</kbd>
                                <kbd class="kbd">6 GB (6144 MiB)</kbd>
                                <kbd class="kbd">8 GB (8192 MiB)</kbd>
                            </div>
                            <span class="text-xs text-base-content/60"
                                >Use 6-8 GB if you have 16+ GB system RAM.</span
                            >
                        </li>
                    </ul>
                    <img src={ramSrc} alt="Selecting RAM Options" />
                </div>
            </section>

            <!-- Launch -->
            <section class="card bg-base-200">
                <div class="card-body">
                    <h2 class="card-title">5) Launch and Connect</h2>
                    <ol class="list-decimal pl-6 space-y-2">
                        <li>
                            Click <span class="badge">Play</span> in Prism to start
                            the modded client.
                        </li>
                        <li>
                            In Minecraft → <span class="badge">Multiplayer</span
                            >
                            → <span class="badge">Add Server</span>.
                        </li>
                        <li>
                            Server Name: <code>Fwends SMP</code> — Address:
                            <code>{serverIP}</code>
                        </li>
                        <li>Join and have fun!</li>
                    </ol>

                    <img src={addServerSrc} alt="Adding Minecraft Server" />

                    <CopyIp class="mt-4 bg-neutral-900" />
                </div>
            </section>

            <!-- Troubleshooting -->
            <section class="collapse bg-base-200">
                <input type="checkbox" />
                <div class="collapse-title text-lg font-medium">
                    Troubleshooting
                </div>
                <div class="collapse-content space-y-2">
                    <p>
                        <span class="font-semibold">Mods missing/disabled?</span
                        >
                        Re-import the zip via <em>Import</em>, not manual.
                    </p>
                    <p>
                        <span class="font-semibold">Crashes on load?</span> Lower
                        shaders, assign more RAM, or update drivers.
                    </p>
                    <p>
                        <span class="font-semibold">Can't join?</span> Double-check
                        the IP and that you're on the same MC/Forge version.
                    </p>
                </div>
            </section>
        </div>
    </div>
</main>
