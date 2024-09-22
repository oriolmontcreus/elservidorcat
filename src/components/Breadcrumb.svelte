<script lang="ts">
    import { createEventDispatcher } from 'svelte';
    import HouseIcon from "lucide-svelte/icons/house";
    import Slash from "lucide-svelte/icons/slash";
    import * as Breadcrumb from "@components/shadcn/ui/breadcrumb";
    
    export let breadcrumbs: Array<{ path: string, title: string }> = [];
    const dispatch = createEventDispatcher();

    function handleLinkClick(event: Event, path: string) {
        event.preventDefault();
        dispatch('navigate', { path });
    }
</script>

<Breadcrumb.Root>
    <Breadcrumb.List>
        <Breadcrumb.Item>
            <Breadcrumb.Link href="/" on:click={(e) => handleLinkClick(e, '/')}>
                <HouseIcon />
            </Breadcrumb.Link>
        </Breadcrumb.Item>
        {#each breadcrumbs as crumb, index}
            <Breadcrumb.Separator>
                <Slash />
            </Breadcrumb.Separator>
            {#if index < breadcrumbs.length - 1}
                <Breadcrumb.Item>
                    <Breadcrumb.Link href={crumb.path} on:click={(e) => handleLinkClick(e, crumb.path)}>
                        {crumb.title}
                    </Breadcrumb.Link>
                </Breadcrumb.Item>
            {:else}
                <Breadcrumb.Item>
                    <Breadcrumb.Page>{crumb.title}</Breadcrumb.Page>
                </Breadcrumb.Item>
            {/if}
        {/each}
    </Breadcrumb.List>
</Breadcrumb.Root>