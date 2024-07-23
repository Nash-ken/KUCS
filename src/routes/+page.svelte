<script>
// @ts-nocheck

   import Navbar from "$lib/components/ui/Navbar/navbar.svelte";

   let width;
    $: mobileView = width <= 768;


</script>

<svelte:window bind:innerWidth={width} />

<div class="flex flex-col">
    <Navbar isMobile={mobileView} />
</div>