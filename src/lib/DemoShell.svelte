<script lang="ts">
  import type { Snippet } from 'svelte';
  import DemoTopNav from './DemoTopNav.svelte';
  let { title = 'Application', children }: { title?: string; children?: Snippet } = $props();
</script>
<div class="shell"><DemoTopNav {title}/><main>{@render children?.()}</main></div>
<style>
  :global(:root){--demo-bg:#f4f6f9;--demo-top:#fff;--demo-text:#1f2937;--demo-border:#dfe4eb;--demo-accent:#315efb;--x07-surface:#fff;--x07-text:#1f2937}
  :global(:root[data-theme='dark']){--demo-bg:#0d1117;--demo-top:#121821;--demo-text:#e8edf4;--demo-border:#242d3a;--demo-accent:#5f7dff;--x07-surface:#151b24;--x07-text:#e8edf4}
  .shell{height:100vh;display:flex;flex-direction:column;overflow:hidden;background:var(--demo-bg);color:var(--demo-text)} main{flex:1;min-height:0;overflow:auto}
</style>
