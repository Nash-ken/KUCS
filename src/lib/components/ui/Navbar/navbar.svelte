<script>
// @ts-nocheck

    import Item from "$lib/components/ui/Navbar/item.svelte";
	import { flyAndScale } from "$lib/utils";
	import { fly, slide } from "svelte/transition";
	import Button from "../button/button.svelte";
	import Dropdown from "../dropdown-menu/dropdown.svelte";
    export let isMobile;
    let menuActive = false;


    function toggleMenu() {
        menuActive = !menuActive;
    }

    function gotoSection(targetID) {
        const targetElement = document.getElementById(targetID);

        if(targetElement) {

            if(menuActive) {
                toggleMenu();
            }

            targetElement.scrollIntoView({
                behavior: "smooth"
            });
        }
        else {
            console.error("Element with ID", targetID, "not found.");
        }
    }
    
</script>


<div class="nav flex justify-between items-center p-5 md:px-10 h-fit z-10">
    {#if isMobile}
        <div class="logo">Logo</div>
        <div class="hamburger z-10">
            {#if menuActive}
                <Button variant={"ghost"} size={"icon"} on:click={toggleMenu}>
                    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" {...$$props}>
                        <path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="m18 6l-6 6m0 0l-6 6m6-6l6 6m-6-6L6 6" color="currentColor" />
                    </svg>
                </Button>
            {:else}
            <Button variant={"ghost"} size={"icon"} on:click={toggleMenu}>
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" {...$$props}>
                    <path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M4 8h16M4 16h16" color="currentColor" />
                </svg>
            </Button>
            {/if}
        </div>


        {#if menuActive}
            <div class="absolute top-0 left-0 w-full h-full bg-background flex flex-col gap-5" transition:flyAndScale>
                <div class="items flex flex-col gap-5 p-10 mt-[82px]">
                    <Item text={"Events"} mobileView={isMobile}></Item>
                    <Item text={"Resources"} mobileView={isMobile}></Item>
                    <Item text={"About Us"} mobileView={isMobile}></Item>
                    
                </div>

                <div class="contact relative px-10">
                    <Button variant={"outline"} size={"full"}>Contact</Button>
                </div>

                <div class="socials flex gap-5 px-10">
                    <Button variant={"outline"} size={"full"}>
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 16 16" {...$$props}>
                            <path fill="currentColor" d="M12.6.75h2.454l-5.36 6.142L16 15.25h-4.937l-3.867-5.07l-4.425 5.07H.316l5.733-6.57L0 .75h5.063l3.495 4.633L12.601.75Zm-.86 13.028h1.36L4.323 2.145H2.865z" />
                        </svg>
                    </Button>

                    <Button variant={"outline"} size={"full"}>
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 16 16" {...$$props}>
                            <path fill="currentColor" d="M8 0C5.829 0 5.556.01 4.703.048C3.85.088 3.269.222 2.76.42a3.9 3.9 0 0 0-1.417.923A3.9 3.9 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7C.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297c.04.852.174 1.433.372 1.942c.205.526.478.972.923 1.417c.444.445.89.719 1.416.923c.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.9 3.9 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417c.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.9 3.9 0 0 0-.923-1.417A3.9 3.9 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046c.78.035 1.204.166 1.486.275c.373.145.64.319.92.599s.453.546.598.92c.11.281.24.705.275 1.485c.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.5 2.5 0 0 1-.599.919c-.28.28-.546.453-.92.598c-.28.11-.704.24-1.485.276c-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.5 2.5 0 0 1-.92-.598a2.5 2.5 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485c-.038-.843-.046-1.096-.046-3.233s.008-2.388.046-3.231c.036-.78.166-1.204.276-1.486c.145-.373.319-.64.599-.92s.546-.453.92-.598c.282-.11.705-.24 1.485-.276c.738-.034 1.024-.044 2.515-.045zm4.988 1.328a.96.96 0 1 0 0 1.92a.96.96 0 0 0 0-1.92m-4.27 1.122a4.109 4.109 0 1 0 0 8.217a4.109 4.109 0 0 0 0-8.217m0 1.441a2.667 2.667 0 1 1 0 5.334a2.667 2.667 0 0 1 0-5.334" />
                        </svg>
                    </Button>

                    <Button variant={"outline"} size={"full"}>
                        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 16 16" {...$$props}>
                            <path fill="currentColor" d="M13.545 2.907a13.2 13.2 0 0 0-3.257-1.011a.05.05 0 0 0-.052.025c-.141.25-.297.577-.406.833a12.2 12.2 0 0 0-3.658 0a8 8 0 0 0-.412-.833a.05.05 0 0 0-.052-.025c-1.125.194-2.22.534-3.257 1.011a.04.04 0 0 0-.021.018C.356 6.024-.213 9.047.066 12.032q.003.022.021.037a13.3 13.3 0 0 0 3.995 2.02a.05.05 0 0 0 .056-.019q.463-.63.818-1.329a.05.05 0 0 0-.01-.059l-.018-.011a9 9 0 0 1-1.248-.595a.05.05 0 0 1-.02-.066l.015-.019q.127-.095.248-.195a.05.05 0 0 1 .051-.007c2.619 1.196 5.454 1.196 8.041 0a.05.05 0 0 1 .053.007q.121.1.248.195a.05.05 0 0 1-.004.085a8 8 0 0 1-1.249.594a.05.05 0 0 0-.03.03a.05.05 0 0 0 .003.041c.24.465.515.909.817 1.329a.05.05 0 0 0 .056.019a13.2 13.2 0 0 0 4.001-2.02a.05.05 0 0 0 .021-.037c.334-3.451-.559-6.449-2.366-9.106a.03.03 0 0 0-.02-.019m-8.198 7.307c-.789 0-1.438-.724-1.438-1.612s.637-1.613 1.438-1.613c.807 0 1.45.73 1.438 1.613c0 .888-.637 1.612-1.438 1.612m5.316 0c-.788 0-1.438-.724-1.438-1.612s.637-1.613 1.438-1.613c.807 0 1.451.73 1.438 1.613c0 .888-.631 1.612-1.438 1.612" />
                        </svg>
                    </Button>
                </div>
                
            </div>
        {/if}

    {:else}
        <div class="logo">logo</div>

        <div class="list flex gap-5">
            <Item text={"Events"} mobileView={isMobile}></Item>
            <Dropdown text={"Resources"}></Dropdown>
            <Item text={"About us"} mobileView={isMobile}></Item>
        </div>

        <Button variant={"outline"}>Contact</Button>
    {/if}
</div>
