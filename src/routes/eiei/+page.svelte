<script lang="ts">
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

<div class="seasonal-container">
  <div bind:this={fxContainer} class="fx-overlay"></div>
</div>

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