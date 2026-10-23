<script setup lang="ts">
withDefaults(defineProps<{
  mode?: 'overview' | 'preview' | 'mix'
}>(), {
  mode: 'overview',
})
</script>

<template>
  <div class="deck-setup" :class="`deck-setup--${mode}`" aria-label="Simplified two-deck DJ setup, not an exact software screenshot">
    <div class="deck-card deck-card--a">
      <div class="deck-heading"><span>DECK A</span><span class="track-badge">PLAYING</span></div>
      <div class="record"><span>A</span></div>
      <div class="deck-track">The track playing now</div>
      <div class="waveform" aria-hidden="true"></div>
      <div class="deck-buttons"><span>LOAD</span><span>▶ / Ⅱ</span><span>SYNC</span></div>
    </div>
    <div class="mixer-card">
      <div class="mixer-label">MIXER</div>
      <div class="output-label">{{ mode === 'mix' ? 'AUDIENCE HEARS A + B' : 'AUDIENCE HEARS A' }}</div>
      <div class="channel-levels" aria-hidden="true"><span></span><span></span></div>
      <div class="mixer-small">Track volumes</div>
      <div class="crossfader"><span></span></div>
      <div class="crossfader-labels"><span>A</span><span>Crossfader</span><span>B</span></div>
    </div>
    <div class="deck-card deck-card--b">
      <div class="deck-heading"><span>DECK B</span><span class="track-badge">{{ mode === 'mix' ? 'PLAYING' : 'UP NEXT' }}</span></div>
      <div class="record"><span>B</span></div>
      <div class="deck-track">The track coming next</div>
      <div class="waveform" aria-hidden="true"></div>
      <div class="deck-buttons"><span>LOAD</span><span>▶ / Ⅱ</span><span>SYNC</span></div>
    </div>
    <div v-if="mode === 'preview'" class="headphone-route">HEADPHONES: preview B privately using headphone CUE</div>
  </div>
</template>
