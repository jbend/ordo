<script lang='ts'>
  import Navigation from "$lib/Navigation.svelte";
import "../app.postcss";

  import { AppShell, AppBar } from '@skeletonlabs/skeleton';
  import { initializeStores, Drawer, getDrawerStore } from '@skeletonlabs/skeleton';
  import { LightSwitch } from '@skeletonlabs/skeleton';

  initializeStores();

  const drawerStore = getDrawerStore();

  function drawerOpen(): void {
	  drawerStore.open({});
  }

</script>

<Drawer>
  <Navigation />
</Drawer>
<!-- svelte-ignore missing-declaration -->
<AppShell slotSidebarLeft="bg-surface-500/5 w-0 lg:w-64">

  <svelte:fragment slot="header">
    <AppBar>Skeleton
      <svelte:fragment slot="lead">
        <div class="flex items-center">
            <button class="lg:hidden btn btn-sm mr-4" on:click={drawerOpen}>
                <span>
                    <svg viewBox="0 0 100 80" class="fill-token w-4 h-4">
                        <rect width="100" height="20" />
                        <rect y="30" width="100" height="20" />
                        <rect y="60" width="100" height="20" />
                    </svg>
                </span>
            </button>
            <strong class="text-xl uppercase">Skeleton</strong>
        </div>
      </svelte:fragment>
    </AppBar>
  </svelte:fragment>

  <svelte:fragment slot="sidebarLeft">
    <div id="sidebar-left" class="hidden lg:block">
      <Navigation />
    </div>
  </svelte:fragment>

  <slot />

</AppShell>