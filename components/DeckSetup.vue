<script setup lang="ts">
import { useSlideContext } from '@slidev/client'
import { computed } from 'vue'

withDefaults(defineProps<{
  mode?: 'overview' | 'preview' | 'mix' | 'transition'
}>(), {
  mode: 'overview',
})

const { $slidev, $page } = useSlideContext()
const isActive = computed(() => $slidev.nav.currentPage === $page.value)
</script>

<template>
  <div class="deck-setup" :class="[`deck-setup--${mode}`, { 'deck-setup--animating': mode === 'transition' && isActive }]" aria-label="Simplified two-deck DJ setup, not an exact software screenshot">
    <div class="deck-card deck-card--a deck-card--audible">
      <div class="deck-heading">
        <span>DECK A</span>
        <span class="track-badge">
          <span class="deck-track--before">PLAYING</span>
          <span v-if="mode === 'transition'" class="deck-track--after">UP NEXT</span>
        </span>
      </div>
      <div class="record"><span>A</span></div>
      <div class="deck-track">
        <span class="deck-track--before">NOW PLAYING</span>
        <span v-if="mode === 'transition'" class="deck-track--after">FIND NEW TRACK</span>
      </div>
      <div class="waveform" aria-hidden="true"></div>
      <div class="deck-buttons"><span>▶ / Ⅱ</span></div>
    </div>
    <div class="mixer-card">
      <div class="mixer-label">MIXER</div>
      <div class="channel-levels" aria-hidden="true"><span></span><span></span></div>
      <div class="mixer-small">Track volumes</div>
      <div class="crossfader"><span></span></div>
      <div class="crossfader-labels">
        <span>A</span><span>Crossfader</span>
        <span class="crossfader-b">B
          <span v-if="mode === 'preview'" class="headphone-cue" aria-label="Deck B in headphones">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
              <path d="M3 14v-3a9 9 0 0 1 18 0v3" />
              <path d="M3 14h4v7H5a2 2 0 0 1-2-2v-5Zm18 0h-4v7h2a2 2 0 0 0 2-2v-5Z" />
            </svg>
          </span>
        </span>
      </div>
    </div>
    <div class="deck-card deck-card--b" :class="{ 'deck-card--audible': mode === 'mix' }">
      <div class="deck-heading">
        <span>DECK B</span>
        <span class="track-badge">
          <span class="deck-track--before">{{ mode === 'mix' ? 'PLAYING' : 'UP NEXT' }}</span>
          <span v-if="mode === 'transition'" class="deck-track--after">PLAYING</span>
        </span>
      </div>
      <div class="record"><span>B</span></div>
      <div class="deck-track">
        <span class="deck-track--before">UP NEXT</span>
        <span v-if="mode === 'transition'" class="deck-track--after">NOW PLAYING</span>
      </div>
      <div class="waveform" aria-hidden="true"></div>
      <div class="deck-buttons"><span>▶ / Ⅱ</span></div>
    </div>
    <div v-if="mode === 'preview'" class="headphone-route">HEADPHONES: preview B privately using headphone CUE</div>
  </div>
</template>
