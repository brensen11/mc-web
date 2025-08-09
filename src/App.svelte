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
    // "/": Home,
    // "/join": Join,
    // "/discord": Discord,
    // "/about": About,
    // "/mods" : Mods,
    "/*": Home,
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
      path: "/mods"
    },
    {
      label: "About",
      path: "/about",
    },
  ];
</script>

<div class="flex flex-col h-screen">
  <Navbar {navLinks} />
  <Router {routes} />
</div>
