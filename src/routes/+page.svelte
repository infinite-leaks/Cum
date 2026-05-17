// Global stats and gallery
<script>
  import { onMount } from 'svelte';
  import { Search, PlayCircle, Heart, Eye } from 'lucide-svelte'; // assume installed later

  let media = [];
  let search = '';

  // Hardcoded or fetch from ../ files but since static, list some
  onMount(() => {
    // In real, use import or API, here example
    media = [
      {name: 'example.gif', url: '/06c170456f995a9794001d6f51bda.gif', type: 'gif'},
      // more...
    ];
  });
</script>

<div class="min-h-screen bg-zinc-950 text-white">
  <!-- Hero -->
  <header class="relative h-[80vh] flex items-center justify-center bg-[radial-gradient(#ff1493_0.5px,transparent_1px)] bg-[length:20px_20px]">
    <div class="text-center z-10">
      <h1 class="text-8xl font-black tracking-tighter bg-gradient-to-r from-pink-500 to-purple-600 bg-clip-text text-transparent">CUM ARCHIVES</h1>
      <p class="text-3xl mt-4 text-pink-400">BBC • Leaks • Pleasure</p>

      <!-- Global Stats XXX -->
      <div class="mt-16 grid grid-cols-4 gap-8 max-w-2xl mx-auto">
        <div class="glass p-6 rounded-3xl text-center">
          <div class="text-6xl font-mono text-pink-500">500+</div>
          <div class="uppercase text-xs tracking-widest">Files</div>
        </div>
        <div class="glass p-6 rounded-3xl text-center">
          <div class="text-6xl font-mono text-purple-500">∞</div>
          <div class="uppercase text-xs tracking-widest">Cumshots</div>
        </div>
        <div class="glass p-6 rounded-3xl text-center">
          <div class="text-6xl font-mono text-cyan-400">2.4M</div>
          <div class="uppercase text-xs tracking-widest">Views</div>
        </div>
        <div class="glass p-6 rounded-3xl text-center">
          <div class="text-6xl font-mono text-amber-400">24/7</div>
          <div class="uppercase text-xs tracking-widest">Leaking</div>
        </div>
      </div>
    </div>
  </header>

  <div class="max-w-7xl mx-auto px-6 py-8">
    <div class="flex gap-4 mb-8">
      <div class="flex-1 relative">
        <Search class="absolute left-4 top-3.5" />
        <input bind:value={search} placeholder="Search leaks..." class="w-full bg-zinc-900 border border-zinc-700 rounded-full pl-12 py-4 focus:border-pink-500" />
      </div>
    </div>

    <div class="columns-1 sm:columns-2 md:columns-3 lg:columns-4 gap-4">
      {#each media as item}
        <div class="mb-6 break-inside-avoid group relative overflow-hidden rounded-2xl">
          <img src={item.url} alt={item.name} class="w-full h-auto object-cover group-hover:scale-105 transition" />
          <div class="absolute bottom-0 left-0 right-0 bg-gradient-to-t from-black p-4">
            <PlayCircle class="inline" /> {item.name}
          </div>
        </div>
      {/each}
    </div>
  </div>
</div>

<style>
  .glass { background: rgba(255,255,255,0.05); backdrop-filter: blur(12px); }
</style>