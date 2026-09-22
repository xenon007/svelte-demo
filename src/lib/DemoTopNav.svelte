<script lang="ts">
  import { ThemeToggle, WindowControls, WindowDragRegion, ZoomControl } from '@xenon007/svelte-wails3';
  let { title = 'Application' }: { title?: string } = $props();
</script>
<header class="topnav">
  <div class="brand"><span class="logo">X</span><strong>{title}</strong></div>
  <nav><a href="/">Home</a><a href="#components">Components</a></nav>
  <div class="grow"><WindowDragRegion label={title} /></div>
  <ZoomControl /><ThemeToggle /><WindowControls />
</header>
<style>
  .topnav { height:46px; display:flex; align-items:center; border-bottom:1px solid var(--demo-border); background:var(--demo-top); position:relative; z-index:20; }
  .brand { display:flex; align-items:center; gap:9px; padding:0 14px; white-space:nowrap; }
  .logo { width:25px; aspect-ratio:1; display:grid; place-items:center; border-radius:7px; background:var(--demo-accent); color:white; font-weight:900; }
  nav { display:flex; align-self:stretch; } nav a { display:flex; align-items:center; padding:0 11px; color:inherit; text-decoration:none; opacity:.65; --wails-draggable:no-drag; app-region:no-drag; }
  nav a:hover { opacity:1; background:color-mix(in srgb,currentColor 6%,transparent); }
  .grow { flex:1; align-self:stretch; min-width:40px; display:flex; }
  @media(max-width:760px){nav{display:none}.brand strong{display:none}}
</style>
