<script>
  import "../app.postcss";

  import { AppShell } from '@skeletonlabs/skeleton';
  import { LightSwitch } from '@skeletonlabs/skeleton';
</script>

<!-- svelte-ignore missing-declaration -->
<AppShell slotSidebarLeft="bg-surface-500/5 w-56 p-4">
  <svelte:fragment slot="sidebarLeft">
    <!-- Insert the list: -->
    <nav class="list-nav">
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
      </ul>
      <LightSwitch />

    </nav>
    <!-- --- -->
  </svelte:fragment>

  <slot />

</AppShell>