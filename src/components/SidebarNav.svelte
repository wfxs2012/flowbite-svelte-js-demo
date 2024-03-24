<script>
    import {Sidebar, SidebarGroup, SidebarItem, SidebarWrapper} from "flowbite-svelte";
    import ArrowRightToBracketSolid from "flowbite-svelte-icons/ArrowRightToBracketSolid.svelte";
    import GridSolid from 'flowbite-svelte-icons/GridSolid.svelte';
    import MailBoxSolid from 'flowbite-svelte-icons/MailBoxSolid.svelte';
    import UserSolid from 'flowbite-svelte-icons/UserSolid.svelte';
    import {location} from 'svelte-spa-router'

    export let items = [];
    $: activeUrl = window.location.pathname;
    let activeClass = 'flex items-center p-2 text-base font-normal text-primary-900 bg-primary-200 dark:bg-primary-700 rounded-lg dark:text-white hover:bg-primary-100 dark:hover:bg-gray-700';
    let nonActiveClass = 'flex items-center p-2 text-base font-normal text-green-900 rounded-lg dark:text-white hover:bg-green-100 dark:hover:bg-green-700';


</script>
{$location} {window.location.pathname}  {activeUrl}
<Sidebar {activeUrl} {activeClass} {nonActiveClass}>
    <SidebarWrapper>
        <SidebarGroup>

            {#each items as {title, href}}

                <SidebarItem label={title} href={'#'+ href} active={true}>
                    <svelte:fragment slot="icon">
                        <UserSolid class="w-5 h-5"/>
                    </svelte:fragment>
                </SidebarItem>

            {/each}

        </SidebarGroup>
    </SidebarWrapper>
</Sidebar>
