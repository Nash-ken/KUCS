<script lang="ts">
    import * as DropdownMenu from "$lib/components/ui/dropdown-menu";
    export let text;
    let open = false;

    function toggleOpen() {
        open = !open;
    }


  </script>
   
  <DropdownMenu.Root>
    <DropdownMenu.Trigger   class="hover:bg-primary-foreground rounded-md">
        <div class:open={open}  class="button px-3 rounded-md flex items-center justify-center gap-3 w-full h-full">
            <p>{text}</p>
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 15 15" {...$$props}>
                <path fill="currentColor" fill-rule="evenodd" d="M3.135 6.158a.5.5 0 0 1 .707-.023L7.5 9.565l3.658-3.43a.5.5 0 0 1 .684.73l-4 3.75a.5.5 0 0 1-.684 0l-4-3.75a.5.5 0 0 1-.023-.707" clip-rule="evenodd" />
            </svg>
        </div>
    </DropdownMenu.Trigger>
    <DropdownMenu.Content  class="my-3">
      <div on:focusin={toggleOpen} on:focusout={toggleOpen}  class="content w-[500px] h-fit flex gap-3 p-3">
        <div class="hero basis-3/5 bg-secondary rounded-md p-3 flex flex-col">

        </div>

        <div class="buttons basis-4/5 flex flex-col gap-3">
            <a href="" class="basis-full rounded-md p-3 hover:bg-secondary flex flex-col"><p>Learning</p><p class="text-muted-foreground text-sm">Access our recommended Leanring Materials.</p></a>
            <a href="" class="basis-full rounded-md p-3 hover:bg-secondary flex flex-col"><p>Practice</p><p class="text-muted-foreground text-sm">Apply your Knowledge by Completing our Challenges.</p></a>
            <a href="" class="basis-full rounded-md p-3 hover:bg-secondary flex flex-col"><p>Courses</p><p class="text-muted-foreground text-sm">View recognized Courses offering Certification and Experience.</p></a>
        </div>
      </div>
    </DropdownMenu.Content>
  </DropdownMenu.Root>


  <style>

    svg {
        transition: rotate .2s;
    }

    .button.open  > svg {
      rotate: 180deg;
    }
  </style>