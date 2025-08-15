<script lang="ts">
  import Navbar from "./lib/Navbar.svelte";
  import Home from "./pages/Home.svelte";
  import Router from "svelte-spa-router";
  import Join from "./pages/Join.svelte";
  import Discord from "./pages/Discord.svelte";
  import About from "./pages/About.svelte";
  import NotFound from "./pages/NotFound.svelte";
  import Mods from "./pages/Mods.svelte";

  const routes = {
    "/": Home,
    "/join": Join,
    "/discord": Discord,
    // "/about": About,
    "/mods": Mods,
    "/*": NotFound,
  };

  const navLinks = [
    {
      label: "Home",
      path: "/",
    },
    {
      label: "How to Join",
      path: "/join",
    },
    {
      label: "Discord",
      path: "/discord",
    },
    {
      label: "Mods",
      path: "/mods",
    },
    // {
    //   label: "About",
    //   path: "/about",
    // },
  ];

  let title = "Fwends SMP";
  let description = "Welcome to the Fwends Survial Multiplayer Server!";
  let image = "../assets/img/Fwends SMP Page Preview.png";
  let url = "http://mc.brensenvillegas.com";
</script>

<svelte:head>
  <title>{title}</title>
  <meta property="og:title" content={title} />
  <meta property="og:description" content={description} />
  <meta property="og:image" content={image} />
  <meta property="og:url" content={url} />
  <meta property="og:type" content="website" />
</svelte:head>

<div class="flex flex-col h-svh">
  <Navbar {navLinks} />
  <Router {routes} />
</div>
