<script lang="ts">
    import Cards from "$lib/Cards.svelte";
    import { onMount, onDestroy } from 'svelte';
  import { createSeasonalFX } from 'seasonalfx';
  import type { ISeasonalFX, Season, Intensity } from 'seasonalfx';

  let fxContainer: HTMLDivElement;
  let fx: ISeasonalFX | null = null;

  let season: Season = 'spring';
  let intensity: Intensity = 'subtle';

  function initFX() {
    if (fxContainer) {
      fx = createSeasonalFX({
        target: fxContainer,
        season: season,
        intensity: intensity,
        maxFPS: 30,
        respectReducedMotion: true,
      });
      fx.start();
    }
  }

  onMount(() => {
    initFX();
  });

  onDestroy(() => {
    fx?.destroy();
  });
</script>

<style>
  .seasonal-container {
    position: relative;
    min-height: 100vh;
    color: white;
    padding: 2rem;
  }

  .fx-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
    pointer-events: none;
  }
</style>
<div class="seasonal-container">
  <div bind:this={fxContainer} class="fx-overlay"></div>
  <div class="h-screen">
    <Cards/>
    <!-- Footer -->
    <footer class="flex justify-center items-end">
        <div class="bg-pink-300 p-3 mb-5 rounded-2xl text-white shadow-md shadow-pink-300 hover:scale-95">
            <i class="fa-solid fa-handshake"></i> <span>ยินดีต้อนรับเข้าสู่เว็บขอพร &gt;</span>
        </div>
    </footer>
    </div>
</div>
